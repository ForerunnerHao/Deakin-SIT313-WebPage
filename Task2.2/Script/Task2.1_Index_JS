// random number --- one neumber one color
var colorArray = [
    "White", "Black", "Navy", "DarkGreen",
    "DarkCyan", "MediumSpringGreen", "Aqua", "DodgerBlue",
    "SeaGreen", "MediumSeaGreen", "SteelBlue", "Indigo",
    "MediumSlateBlue", "Maroon", "DarkRed", "DarkSeaGreen",
    "DarkViolet", "Sienna", "LightBlue", "IndianRed"
];

//Color name's RGB value
var colorArray_RGB = [{
        //White
        R: 255,
        G: 255,
        B: 255
    },
    {
        //Black
        R: 0,
        G: 0,
        B: 0
    }, {
        //Navy
        R: 0,
        G: 0,
        B: 128
    }, {
        //DarkGreen
        R: 0,
        G: 100,
        B: 0
    },
    {
        //DarkCyan
        R: 0,
        G: 139,
        B: 139
    }, {
        //MediumSpringGreen
        R: 0,
        G: 250,
        B: 154
    }, {
        //Aqua
        R: 0,
        G: 255,
        B: 255
    }, {
        //DodgerBlue
        R: 30,
        G: 144,
        B: 255
    },
    {
        //SeaGreen
        R: 46,
        G: 139,
        B: 87
    }, {
        //MediumSeaGreen
        R: 60,
        G: 179,
        B: 113
    }, {
        //SteelBlue
        R: 70,
        G: 130,
        B: 180
    }, {
        //Indigo
        R: 75,
        G: 0,
        B: 130
    },
    {
        //MediumSlateBlue
        R: 123,
        G: 104,
        B: 238
    }, {
        //Maroon
        R: 128,
        G: 0,
        B: 0
    }, {
        //DarkRed
        R: 139,
        G: 0,
        B: 0
    }, {
        //DarkSeaGreen
        R: 143,
        G: 188,
        B: 143
    },
    {
        //DarkViolet
        R: 148,
        G: 0,
        B: 211
    }, {
        //Sienna
        R: 160,
        G: 82,
        B: 45
    }, {
        //LightBlue
        R: 173,
        G: 216,
        B: 230
    }, {
        //IndianRed
        R: 205,
        G: 92,
        B: 92
    },
]

var mainBody = document.getElementById("mainBody");
var topContent = document.getElementById("navigationMenu");
var midContent = document.getElementById("midContent");
var bottomContent = document.getElementById("ChangeColorButton");

//Click button event
var btn = document.getElementById('colorPicker').onclick = () => {

    beginColorNum = randomNum_0_20();
    endColorNum = randomNum_0_20();
    while (beginColorNum == endColorNum) {
        endColorNum = randomNum_0_20();
    }

    // Get color name
    var beginColor = colorArray[beginColorNum];
    var endColor = colorArray[endColorNum];

    // Get color name's RGB value
    var beginColor_RGB = colorArray_RGB[beginColorNum];
    var endColor_RGB = colorArray_RGB[endColorNum];
    var midColor_RGB = midRGB(beginColor_RGB, endColor_RGB);

    // Convert RGB to YIQ 
    var YIQ_begin = YIQ(beginColor_RGB);
    var YIQ_mid = YIQ(midColor_RGB);
    var YIQ_end = YIQ(endColor_RGB);

    //  test codes
    //  console.log(`RGB(${beginColor_RGB.R},${beginColor_RGB.G},${beginColor_RGB.B})`);
    //  console.log(`RGB(${midColor_RGB.R},${midColor_RGB.G},${midColor_RGB.B})`);
    //  console.log(`RGB(${endColor_RGB.R},${endColor_RGB.G},${endColor_RGB.B})`);
    //  console.log(`beginColorNum:${beginColorNum},colorName:${beginColor},RGB(${beginColor_RGB.R},${beginColor_RGB.G},${beginColor_RGB.B})`);
    //  console.log(`beginColorNum:${endColorNum},colorName:${endColor},RGB(${endColor_RGB.R},${endColor_RGB.G},${endColor_RGB.B})`);
    //  console.log(mainBody.style.backgroundColor);

    // Top content color change
    topContent.childNodes[1].style.color = blackOrWhite(YIQ_begin);
    topContent.childNodes[3].style.color = blackOrWhite(YIQ_begin);
    topContent.childNodes[5].style.color = blackOrWhite(YIQ_begin);

    // Middle content color change
    midContent.style.color = blackOrWhite(YIQ_mid);

    // Bottom content color change
    bottomContent.style.color = blackOrWhite(YIQ_end);

    // Webpage background color change
    mainBody.style.background = `linear-gradient(${beginColor},${endColor})`;

};


function randomNum_0_20() {
    return Math.floor(Math.random() * 20);
}

function blackOrWhite(num) {
    if (num > 125) {
        return "black";
    } else {
        return "white";
    }
}

function YIQ(Color_RGB) {
    return (Color_RGB.R * 0.299 + Color_RGB.G * 0.587 + Color_RGB.B * 0.114);
}

function midRGB(beginColor_RGB, endColor_RGB) {
    var MaxR = beginColor_RGB.R > endColor_RGB.R ? beginColor_RGB.R : endColor_RGB.R;
    var MinR = beginColor_RGB.R < endColor_RGB.R ? beginColor_RGB.R : endColor_RGB.R;
    var MaxG = beginColor_RGB.G > endColor_RGB.G ? beginColor_RGB.G : endColor_RGB.G;
    var MinG = beginColor_RGB.G < endColor_RGB.G ? beginColor_RGB.G : endColor_RGB.G;
    var MaxB = beginColor_RGB.B > endColor_RGB.B ? beginColor_RGB.B : endColor_RGB.B;
    var MinB = beginColor_RGB.B < endColor_RGB.B ? beginColor_RGB.B : endColor_RGB.B;
    var R = Math.floor(MinR + (MaxR - MinR) / 2);
    var G = Math.floor(MinG + (MaxG - MinG) / 2);
    var B = Math.floor(MinB + (MaxB - MinB) / 2);
    return {
        R,
        G,
        B
    };
}
