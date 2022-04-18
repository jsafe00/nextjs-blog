---
slug: php-interface
title: PHP Interface
description: 
date: 18-April-2022
---

In simple terms, think about Interface as the Skeleton or Blueprint for your class. It specifies the lists of all such methods that a class must implement.

Sample:

```
    interface Coffee {
        public function makeAmericano();
        public function makeCappuccino();
        public function makeEspresso();
        public function makeFrappuccino();
        public function makeIcedCoffee();
        public function makeLatte();
    }

    class AllInOneCoffee implements Coffee {
        public function makeAmericano() {
            echo "Making Americano Coffee";
        }

        public function makeCappuccino() {
            echo "Making Cappuccino Coffee";
        }

        public function makeEspresso() {
            echo "Making Espresso Coffee";
        }

        public function makeFrappuccino() {
            echo "Making Frappuccino Coffee";
        }

        public function makeIcedCoffee() {
            echo "Making Iced Coffee";
        }

        public function makeLatte() {
            echo "Making Latte Coffee";
        }
    }

    $coffee = new AllInOneCoffee();
    $coffee->makeAmericano();
    $coffee->makeCappuccino();
    $coffee->makeEspresso();
    $coffee->makeFrappuccino();
    $coffee->makeIcedCoffee();
    $coffee->makeLatte();


Output:

    Making Americano Coffee
    Making Cappuccino Coffee
    Making Espresso Coffee
    Making Frappuccino Coffee
    Making Iced Coffee
    Making Latte Coffee

```

