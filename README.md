# AstroAlgo
AstroAlgo is an astronomical algorithms library, written in __.NET Standard__. It can be used to calculate astronomical data, like equator and ecliptic coordinate, planet rise and down time, elevation angle... Planets data are based on the planetary theory VSOP87.

__Don't use it for scientific calculations.__

## Reference
* Astronomical Algorithms, First Edition by Jean Meeus
* Full-precision VSOP87 theory data - http://www.neoprogrammics.com/vsop87/

## How to Get
* NuGet Package Manager
```
PM> Install-Package AstroAlgo -Version 1.0.0
```
* Add AstroAlgo.dll to project

## Introduction
* Calculate the Julian day
* Sidereal time and Zone time converter
* Coordinate system basic tools, include nutation, coordinate converter...
* Angle to HoursMinutesSeconds or to DegreeMinutesSeconds
* Eight planets, in the solar system, rise and down time, equator coordinate, ecliptic coordinate...
* ......

__Code Map__
![](https://github.com/ZhangGaoxing/AstroAlgo/blob/master/Doc/class.png)

## Version History
### 2017/9/16 1.0.0
First Version

## How to Use
After add reference to project
```C#
Venus v = new Venus(34.27, 117.15);

Console.WriteLine(v.Rise);
Console.WriteLine(v.Culmination);
Console.WriteLine(v.Down);
Console.WriteLine();

Console.WriteLine(v.ElevationAngle);
Console.WriteLine(v.Azimuth);
Console.WriteLine();

Console.WriteLine(v.ToSun);
Console.WriteLine(v.ToEarth);
```
