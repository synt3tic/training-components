<template>
  <div class="card">
    <h3 class="card__header">Headline</h3>
    <div v-for="item in currentDataArray" :key="item.id" class="card__information">
      <div class="information__title">{{ item.title }}</div>
      <div class="information__value">{{ item.value }}</div>
    </div>
    <button :class="buttonClasses" @click="expandCard"></button>
  </div>
</template>

<script>

export default {
  data() {
    return {
      vehicleInformation: [
        {
          id: 1,
          title: "Максимальная скорость, км/ч:",
          value: "250"
        },
        {
          id: 2,
          title: "Разгон до 100 км/ч, сек:",
          value: "15"
        },
        {
          id: 3,
          title: "Разгон до 100 км/ч, сек:",
          value: "15"
        },
        {
          id: 4,
          title: "Разгон до 100 км/ч, сек:",
          value: "15"
        },
        {
          id: 5,
          title: "Разгон до 100 км/ч, сек:",
          value: "15"
        },
        {
          id: 6,
          title: "Разгон до 100 км/ч, сек:",
          value: "15"
        },
        {
          id: 7,
          title: "Разгон до 100 км/ч, сек:",
          value: "15"
        },
        {
          id: 8,
          title: "Разгон до 100 км/ч, сек:",
          value: "15"
        },
        {
          id: 9,
          title: "Разгон до 100 км/ч, сек:",
          value: "15"
        },
      ],
      isCardExpended: false
    }
  },
  computed: {
    currentDataArray() {
      if (this.isCardExpended) {
        return this.vehicleInformation
      } else {
        const currentVehicleInformation = []
        for (let i = 0; i < 3; i++) {
          currentVehicleInformation.push(this.vehicleInformation[i])
        }
        return currentVehicleInformation
      }
    },
    buttonClasses() {
      return ["card__icon", {
        "card__icon_collapse": this.isCardExpended,
        "card__icon_expand": !this.isCardExpended,
      }]
    }
  },
  methods: {
    expandCard() {
      this.isCardExpended = !this.isCardExpended
      console.log(this.im())
    },
  }
}
</script>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  align-items: center;
  border-radius: 5px;
  background-color: rgb(224, 220, 224);
  padding: 15px;
  gap: 15px;
}

.card__header {
  font-family: Arial, Helvetica, sans-serif;
  font-weight: 100;
  align-self: flex-start;
  margin: 15px 0 0;
}

.card__information {
  display: flex;
  align-items: center;
  width: 550px;
  background-color: aliceblue;
  border-radius: 5px;
  padding: 10px 15px;
  font-family: Arial, Helvetica, sans-serif;
  font-weight: 100;
  align-self: flex-start;
  font-size: 14px;
}

.information__title {
  color: gray;
  width: 275px;
}

.information__value {
  width: 275px;
  text-align: end;
  overflow-wrap: break-word;
}

.card__icon {
  margin: 5px;
  cursor: pointer;
  align-self: flex-end;
  border: none;
  background: none;
  width: 17.5px;
  height: 10px;
}

.card__icon_collapse {
  background-image: url(../images/icon-collapse.svg);
}

.card__icon_expand {
  background-image: url(../images/icon-expand.svg);
}
</style>