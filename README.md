puppeteer-extra-plugin-stealth GitHub Workflow Status Discord npm
A plugin for puppeteer-extra to prevent detection.



Install
yarn add puppeteer-extra-plugin-stealth
# - or -
npm install puppeteer-extra-plugin-stealth
If this is your first puppeteer-extra plugin here's everything you need:

yarn add puppeteer puppeteer-extra puppeteer-extra-plugin-stealth
# - or -
npm install puppeteer puppeteer-extra puppeteer-extra-plugin-stealth
Usage
// puppeteer-extra is a drop-in replacement for puppeteer,
// it augments the installed puppeteer with plugin functionality
const puppeteer = require('puppeteer-extra')

// add stealth plugin and use defaults (all evasion techniques)
const StealthPlugin = require('puppeteer-extra-plugin-stealth')
puppeteer.use(StealthPlugin())

// puppeteer usage as normal
puppeteer.launch({ headless: true }).then(async browser => {
  console.log('Running tests..')
  const page = await browser.newPage()
  await page.goto('https://bot.sannysoft.com')
  await page.waitForTimeout(5000)
  await page.screenshot({ path: 'testresult.png', fullPage: true })
  await browser.close()
  console.log(`All done, check the screenshot. ✨`)
})
