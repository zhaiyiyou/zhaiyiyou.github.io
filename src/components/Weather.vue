<template>
  <div class="weather" v-if="weatherData.adCode.city && weatherData.weather.weather">
    <span>{{ weatherData.adCode.city }}&nbsp;</span>
    <span>{{ weatherData.weather.weather }}&nbsp;</span>
    <span>{{ weatherData.weather.temperature }}℃</span>
    <span class="sm-hidden">
      &nbsp;{{
        weatherData.weather.winddirection?.endsWith("风")
          ? weatherData.weather.winddirection
          : weatherData.weather.winddirection + "风"
      }}&nbsp;
    </span>
    <span class="sm-hidden">{{ weatherData.weather.windpower }}&nbsp;级</span>
  </div>
  <div class="weather" v-else>
    <span>天气数据获取失败</span>
  </div>
</template>

<script setup>
import { getAdcode, getWeather, getOtherWeather } from "@/api";
import { Error } from "@icon-park/vue-next";

// 高德开发者 Key
const mainKey = import.meta.env.VITE_WEATHER_KEY;

// 天气数据
const weatherData = reactive({
  adCode: {
    city: null, // 城市
    adcode: null, // 城市编码
  },
  weather: {
    weather: null, // 天气现象
    temperature: null, // 实时气温
    winddirection: null, // 风向描述
    windpower: null, // 风力级别
  },
});

// 获取天气数据
const getWeatherData = async () => {
  try {
    // 获取地理位置信息
    if (!mainKey) {
      console.log("未配置，使用备用天气接口");
      const result = await getOtherWeather();
      console.log(result);
      const current = result.current_condition[0];
      const area = result.nearest_area[0];
      weatherData.adCode = {
        city: area.areaName[0].value,
      };
      weatherData.weather = {
        weather: current.lang_zh?.[0]?.value || current.weatherDesc[0].value,
        temperature: current.temp_C,
        winddirection: compassToChinese(current.winddir16Point),
        windpower: kmhToBeaufort(current.windspeedKmph),
      };
    } else {
      // 获取 Adcode
      const adCode = await getAdcode(mainKey);
      console.log(adCode);
      if (adCode.infocode !== "10000") {
        throw "地区查询失败";
      }
      weatherData.adCode = {
        city: adCode.city,
        adcode: adCode.adcode,
      };
      // 获取天气信息
      const result = await getWeather(mainKey, weatherData.adCode.adcode);
      weatherData.weather = {
        weather: result.lives[0].weather,
        temperature: result.lives[0].temperature,
        winddirection: result.lives[0].winddirection,
        windpower: result.lives[0].windpower,
      };
    }
  } catch (error) {
    console.error("天气信息获取失败:" + error);
    onError("天气信息获取失败");
  }
};

// 罗盘风向转中文
const compassToChinese = (dir) => {
  const map = {
    N: "北",
    NNE: "东北偏北",
    NE: "东北",
    ENE: "东北偏东",
    E: "东",
    ESE: "东南偏东",
    SE: "东南",
    SSE: "东南偏南",
    S: "南",
    SSW: "西南偏南",
    SW: "西南",
    WSW: "西南偏西",
    W: "西",
    WNW: "西北偏西",
    NW: "西北",
    NNW: "西北偏北",
  };
  return map[dir] || dir;
};

// 风速(km/h) 转 风力等级
const kmhToBeaufort = (kmh) => {
  const speed = Number(kmh);
  if (speed < 1) return 0;
  if (speed <= 5) return 1;
  if (speed <= 11) return 2;
  if (speed <= 19) return 3;
  if (speed <= 28) return 4;
  if (speed <= 38) return 5;
  if (speed <= 49) return 6;
  if (speed <= 61) return 7;
  if (speed <= 74) return 8;
  if (speed <= 88) return 9;
  if (speed <= 102) return 10;
  if (speed <= 117) return 11;
  return 12;
};

// 报错信息
const onError = (message) => {
  ElMessage({
    message,
    icon: h(Error, {
      theme: "filled",
      fill: "#efefef",
    }),
  });
  console.error(message);
};

onMounted(() => {
  // 调用获取天气
  getWeatherData();
});
</script>
