# ZYGAL-Assignment-Dec-22
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Zygal Assignment Advanced</title>
    <style>
        .main-div {
            border: 1px solid;
            /* display: flex; */
            justify-content: center;
            height: 100%;
            padding: 3%;
        }

        .dropdown-div {
            display: flex;
            justify-content: center;
        }

        .months,
        .years {
            padding: 2%;
            margin: 2%;
            /* position: relative; */
            font-family: 'Times New Roman';
            font-size: 150%;
        }

        .input {
            padding: 1% 1%;
            font-family: 'Times New Roman';
            font-size: 150%;
            width: 15%;
        }

        .button {
            padding: 1% 1%;
            font-family: 'Times New Roman';
            font-size: 150%;
            width: 10%;
        }

        ul {
            list-style-type: none;
        }

        .weekdays {
            margin: 0%;
            padding: 1% 0%;
            border: 1px solid;
        }

        .weekdays li {
            display: inline-block;
            width: 13%;
            text-align: center;
            padding: 1% 0%;
            font-size: 20px;
        }

        .days {
            padding: 1% 0%;
            margin: 0;
            border: 1px solid;
        }

        .days li {
            list-style-type: none;
            display: inline-block;
            width: 13%;
            text-align: center;
            margin-bottom: 5px;
            font-size: 20px;
            padding: 1% 0%;
        }

    </style>
</head>

<body>
    <div class="main-div">
        <div>
            <div class="dropdown-div">
                <select name="months" id="months" class="months" onchange="monthsDays()">
                    <option disabled selected value="0">Select Month</option>
                    <option value="jan">January</option>
                    <option value="feb">February</option>
                    <option value="mar">March</option>
                    <option value="apr">April</option>
                    <option value="may">May</option>
                    <option value="jun">June</option>
                    <option value="jul">July</option>
                    <option value="aug">Augest</option>
                    <option value="sep">September</option>
                    <option value="oct">October</option>
                    <option value="nov">November</option>
                    <option value="dec">December</option>
                </select>
                <select name="years" id="years" class="years" onchange="monthsDays()">
                    <option disabled selected>Select Year</option>
                    <option value="1999">1999</option>
                    <option value="2000">2000</option>
                    <option value="2001">2001</option>
                    <option value="2002">2002</option>
                    <option value="2003">2003</option>
                    <option value="2004">2004</option>
                    <option value="2005">2005</option>
                    <option value="2006">2006</option>
                    <option value="2007">2007</option>
                    <option value="2008">2008</option>
                    <option value="2009">2009</option>
                    <option value="2010">2010</option>
                    <option value="2011">2011</option>
                    <option value="2012">2012</option>
                    <option value="2013">2013</option>
                    <option value="2014">2014</option>
                    <option value="2015">2015</option>
                    <option value="2016">2016</option>
                    <option value="2017">2017</option>
                    <option value="2018">2018</option>
                    <option value="2019">2019</option>
                    <option value="2020">2020</option>
                    <option value="2021">2021</option>
                    <option value="2022">2022</option>
                </select>
            </div>
            <div>
                <ul class="weekdays">
                    <li>MON</li>
                    <li>TUE</li>
                    <li>WED</li>
                    <li>THR</li>
                    <li>FRI</li>
                    <li>SAT</li>
                    <li>SUN</li>
                </ul>

                <ul class="days" id="days-of-month">
                    <h5 align="center"><i>Please select "Month" or "Year" to display days</i></h5>
                </ul>

            </div>
            <br><br>
            <div>
                <form>
                    <input type="number" class="input" id="enteredDay" placeholder="Enter any day" onchange="monthsDays()"
                        min="1" max="31"></input>
                    <button type="button" class="button" onclick="monthsDays()">Enter</button>
                </form>
            </div>
        </div>
    </div>

    <script>

        var enteredDay = document.getElementsByTagName("input")[0].value;

        var getYear = () => document.getElementById("years").value;
        var getDays = () => {

            var selectedMonth = document.getElementById("months").value;
            var days = 31;
            if ((selectedMonth == 'apr') || (selectedMonth == 'jun') || (selectedMonth == 'sep') || (selectedMonth == 'nov')) {
                return days = 30;
            } else if (selectedMonth == "feb") {
                let year = getYear();
                const leap = new Date(year, 1, 29).getDate() === 29;
                if (leap) {
                    return days = 29;
                } else {
                    return days = 28;
                }
            } else {
                return days = 31;
            }
        }

        var daysOfMonth = () => {
            let days = getDays();
            var str = '<li></li>'.repeat(3);
            for (let day = 1; day <= days; day++) {
                if (document.getElementById("enteredDay").value == day) {
                    if ("green" == document.getElementById("enteredDay").style.backgroundColor) {
                        str = str + (`<li id=${day}>${day}</li>`);
                    } else {
                        str = str + (`<li id=${day}><span style="background: green; padding: 10px 35px">${day}<span></li>`);
                    }
                } else {
                    str = str + (`<li>${day}</li>`);
                }
            }
            return str;
        }
        var monthsDays = () => document.getElementById("days-of-month").innerHTML = daysOfMonth();
    </script>
</body>

</html>
