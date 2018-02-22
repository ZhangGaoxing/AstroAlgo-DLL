# AstroAlgo
AstroAlgo is an astronomical algorithms library, written in __.NET Standard__. It can be used to calculate astronomical data, like equator and ecliptic coordinate, planet rise and down time, elevation angle... Planets data are based on the planetary theory VSOP87.

NuGet : https://www.nuget.org/packages/AstroAlgo/

__Don't use it for scientific calculations.__

## Catalogue
- [Reference](#reference)
- [How to Get](#how-to-get)
- [Introduction](#introduction)
- [Version History](#version-history)
- [How to Use](#how-to-use)
  - [Julian Day](#julian-day)
  - [Sidereal Time](#sidereal-time)
  - [Ecliptic Obliquity](#ecliptic-obliquity)
  - [Coordinate Converter](#coordinate-converter)
  - [Planets Data](#planets-data)

## Reference
* Astronomical Algorithms, First Edition by Jean Meeus
* Full-precision VSOP87 theory data - http://www.neoprogrammics.com/vsop87/

## How to Get
* NuGet Package Manager
```
PM> Install-Package AstroAlgo -Version 1.0.1
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
### 2018-2-22 1.0.3 
* Now you can calculate solar terms
* Fixed bugs
### 2017-9-24 1.0.2 
* Now you can custom timezone when initialize the objects of SolarSystem
* Fixed many many many bugs...
### 2017-9-23 1.0.1 
* Improve equinoxes and solstices accuracy 
* ElevationAngle2Time() return "0:0:0" if time dose not exist
### 2017/9/16 1.0.0
First Version

## How to Use
After add reference to project
### Julian Day
```C#
// Julian to Calendar
double julian = Julian.ToJulianDay(DateTime.Now);
// Calendar to Julian
DateTime now = Julian.ToCalendarDay(julian);
```
### Sidereal Time
```C#
// Zone Time, Local Zone, Longitude
double angle = SiderealTime.LocalSiderealTime(DateTime.Now, TimeZoneInfo.Local, 117.18);
string time = BasicTools.Angle2HMS(angle);

Console.WriteLine(time);
```
### Ecliptic Obliquity
```C#
double angle = CoordinateSystem.EclipticObliquity(DateTime.Now);
```
### Coordinate Converter
```C#
Equator equator = Sun.EquatorialCoordinate(DateTime.Now);
Ecliptic ecliptic = CoordinateSystem.Equatorial2Ecliptic(equator);

Console.WriteLine(ecliptic.Latitude);
Console.WriteLine(ecliptic.Longitude);
```
### Planets Data
```C#
// Your latitude and longitude
Venus v = new Venus(34.27, 117.15, TimeZoneInfo.Local);

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
