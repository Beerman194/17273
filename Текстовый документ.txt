$(document).ready(function() {

                // Изменение контента
                $("#change-content").click(function() {
                    $("#main-title").text("Контент изменен!");
                });
    
                // Показ/Скрытие элемента
                $("#toggle-paragraph").click(function() {
                    $("#paragraph").toggleClass("hidden");
                });
    
                // Выделение элемента
                $("#highlight").click(function() {
                    $("#main-title").toggleClass("highlight");
                });
    
                // Анимация
                $("#animate").click(function() {
                    $("#animate-box").animate({
                        width: "200px",
                        height: "200px",
                        opacity: 0.5
                    }, 1000).animate({
                        width: "100px",
                        height: "100px",
                        opacity: 1
                    }, 1000);
                });
    
            });
    const app = new Vue({
              el: "#app",
              data: {
                athletes: [
                  { name: "Хесус Оливарес", weight: 1152.5 },
                  { name: "Кирилл Сарычев", weight: 1082.5 },
                  { name: "Андрей Маланичев", weight: 1140 },
                ],
                newAthleteName: "",
                newAthleteWeight: null,
                showInfo: true,
              },
              methods: {
                addAthlete() {
                  if (this.newAthleteName && this.newAthleteWeight) {
                    this.athletes.push({
                      name: this.newAthleteName,
                      weight: this.newAthleteWeight,
                    });
                    this.newAthleteName = "";
                    this.newAthleteWeight = null;
                  } else {
                    alert("Введите имя и вес спортсмена!");
                  }
                },
                toggleInfo() {
                  this.showInfo = !this.showInfo;
                },
                sortAthletes() {
                  this.athletes.sort((a, b) => b.weight - a.weight); // Сортировка по убыванию веса
                },
              },
            });
