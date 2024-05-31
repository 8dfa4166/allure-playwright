https://zenn.dev/reflex4qa/articles/01029546ab6e0e

## preconditions
```
sudo apt update
sudo apt install dpkg 

sudo apt-get update
sudo apt-get install default-jre-headless

sudo apt --fix-broken install

wget https://github.com/allure-framework/allure2/releases/download/2.29.0/allure_2.29.0-1_all.deb
sudo chmod +x allure_2.29.0-1_all.deb
sudo dpkg -i allure_2.29.0-1_all.deb

allure --version
export _JAVA_OPTIONS="-Djava.awt.headless=true"
```

## install
```
npm install --save-dev allure-commandline
npm install --save-dev @playwright/test allure-playwright
```

## setting
playwright.config.ts
```
# add
import { testPlanFilter } from "allure-playwright/dist/testplan";

# add
  grep: testPlanFilter(),
  reporter: [["line"], ["allure-playwright"]],
```

## execute
```
npx playwright test
npx allure serve allure-results

```