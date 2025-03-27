<script>
export default {
  methods: {
    calculateDate(start, end) {
      const [startMonth, startYear] = start.split('.').map(Number)
      const [endMonth, endYear] = end.split('.').map(Number)

      let months = (endYear - startYear) * 12 + (endMonth - startMonth)
      const years = Math.floor(months / 12)
      months -= years * 12

      let result = ''
      if (years > 0) result += `${years} ${years === 1 ? 'rok' : 'lata'}`
      if (months > 0) result += ` ${months} mies.`

      return result.trim()
    },

    calculateDateBackNow(start) {
      const [startMonth, startYear] = start.split('.').map(Number)

      const now = new Date()
      const currentMonth = now.getMonth() + 1
      /**
       * * getMonth() return months 0-11
       */
      const currentYear = now.getFullYear()

      let months = (currentYear - startYear) * 12 + (currentMonth - startMonth)
      const years = Math.floor(months / 12)
      months = months % 12

      let result = ''
      if (years > 0) result += `${years} ${years === 1 ? 'rok' : 'lata'}`
      if (months > 0) result += ` ${months} mies.`
      return result.trim()
    },
  },
}
</script>

<template>
  <section>
    <ul>
      <li>
        <a
          >04.2025 - obecnie
          <span> ({{ calculateDateBackNow('04.2025') }}) </span>
        </a>
        <h3>
          ▶ Wyższa Szkoła Informatyki i Zarządzania w siedzibą w Rzeszowie
        </h3>
        <p>Kierunek: Cyberbezpieczeństwo</p>
        <p>Wykształcenie: <b>Wyższe - Magister</b></p>
        <p></p>
      </li>
      <li>
        <a
          >10.2021 - 03.2025
          <span> ({{ calculateDate('10.2021', '03.2025') }}) </span>
        </a>
        <h3>
          ▶ Wyższa Szkoła Informatyki i Zarządzania w siedzibą w Rzeszowie
        </h3>
        <p>Kierunek: Informatyka - Technologie Internetowe i Mobilne</p>
        <p>Wykształcenie: <b>Wyższe - Inżynier</b></p>
        <p></p>
      </li>
      <li>
        <a
          >09.2018 - 05.2021
          <span> ({{ calculateDate('09.2018', '05.2021') }}) </span>
        </a>
        <h3>▶ II Liceum Ogólnokształcące im. Konstytucji 3 maja w Krośnie</h3>
        <p>Kierunek: Matematyczno-Fizyczny z Informatyką</p>
        <p>Wykształcenie: <b>Średnie</b></p>
      </li>
    </ul>
  </section>
</template>

<style scoped>
li {
  list-style-type: none;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin: 30px;
}

span {
  font-size: 0.8em;
  color: gray;
}

h3,
p,
a,
span {
  margin: 2px;
  padding: 0;
}
</style>
