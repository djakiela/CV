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

    calculateMultiDate(periods) {
      let totalMonths = 0

      periods.forEach(([start, end]) => {
        const [startMonth, startYear] = start.split('.').map(Number)
        const [endMonth, endYear] = end.split('.').map(Number)

        const months = (endYear - startYear) * 12 + (endMonth - startMonth)
        totalMonths += months
      })

      const years = Math.floor(totalMonths / 12)
      const months = totalMonths % 12

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
          >06.2023 - 09.2023 oraz 10.2024 - 11.2024
          <span>
            ({{
              calculateMultiDate([
                ['06.2023', '09.2023'],
                ['10.2024', '11.2024'],
              ])
            }})
          </span>
        </a>
        <h3>▶ Praktyka zawodowa</h3>
        <p>Praktyka zawodowa w firmie <strong>Moonbite</strong></p>
        <p>Czas trwania 06.2023-08.2023 oraz 10.2024-11.2024</p>
        <p>Opis: Nauka programowania w języku Vue.js</p>
      </li>
      <li>
        <a
          >06.2022 - 09.2022
          <span> ({{ calculateDate('06.2022', '09.2022') }}) </span>
        </a>
        <h3>▶ Praktyka zawodowa</h3>
        <p>Praktyka zawodowa w firmie <strong>Kompmacher</strong></p>
        <p>Czas trwania 06.2022-09.2022</p>
        <p>Opis: Nauka o serwisowaniu sprzętu komputerowego</p>
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

a {
  font-size: 0.9em;
}

h3,
p,
a,
span {
  margin: 2px;
  padding: 0;
}
</style>
