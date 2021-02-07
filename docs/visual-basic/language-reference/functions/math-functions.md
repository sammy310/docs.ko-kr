---
description: '자세한 정보: 수학 함수 (Visual Basic)'
title: 수치 연산 함수
ms.date: 01/27/2020
helpviewer_keywords:
- math functions, Visual Basic
- arithmetic operations, math functions
- math routines
- Atn function
ms.assetid: 4d2d82e7-6924-42fe-a4a7-b4dd5bebbd0c
ms.openlocfilehash: d6ab82e45a17c0b1e1ee9f7df54936cd5420ef2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731154"
---
# <a name="math-functions-visual-basic"></a>수학 함수(Visual Basic)

클래스의 메서드는 <xref:System.Math?displayProperty=nameWithType> 삼각, 로그 및 기타 일반 수학 함수를 제공 합니다.

## <a name="remarks"></a>설명

다음 표에서는 클래스의 메서드를 보여 줍니다 <xref:System.Math?displayProperty=nameWithType> . 이러한 작업은 Visual Basic 프로그램에서 사용할 수 있습니다.
  
|.NET 메서드|설명|
|---------------------------|-----------------|
|<xref:System.Math.Abs%2A>|숫자의 절대값을 반환합니다.|
|<xref:System.Math.Acos%2A>|코사인을 적용했을 때 지정된 숫자가 나오는 각도를 반환합니다.|
|<xref:System.Math.Asin%2A>|사인을 적용했을 때 지정된 숫자가 나오는 각도를 반환합니다.|
|<xref:System.Math.Atan%2A>|탄젠트를 적용했을 때 지정된 숫자가 나오는 각도를 반환합니다.|
|<xref:System.Math.Atan2%2A>|탄젠트를 적용했을 때 지정된 두 숫자의 몫이 나오는 각도를 반환합니다.|
|<xref:System.Math.BigMul%2A>|2 32 비트 숫자의 전체 곱을 반환 합니다.|
|<xref:System.Math.Ceiling%2A>|지정 된 또는 보다 크거나 같은 최소 정수 값을 반환 합니다 `Decimal` `Double` .|
|<xref:System.Math.Cos%2A>|지정된 각도의 코사인을 반환합니다.|
|<xref:System.Math.Cosh%2A>|지정된 각도의 하이퍼볼릭 코사인을 반환합니다.|
|<xref:System.Math.DivRem%2A>|2 32 비트 또는 64 비트 부호 있는 정수의 몫을 반환 하 고 나머지를 출력 매개 변수로 반환 합니다.|
|<xref:System.Math.Exp%2A>|지정 된 지 수로 거듭제곱 한 e (자연 지 수의 밑)를 반환 합니다.|
|<xref:System.Math.Floor%2A>|지정 된 또는 숫자 보다 작거나 같은 최대 정수를 반환 합니다 `Decimal` `Double` .|
|<xref:System.Math.IEEERemainder%2A>|지정 된 숫자를 지정 된 다른 숫자로 나눈 나머지를 반환 합니다.|
|<xref:System.Math.Log%2A>|지정 된 숫자의 자연 (밑 e) 로그 또는 지정 된 밑에 있는 지정 된 숫자의 로그를 반환 합니다.|
|<xref:System.Math.Log10%2A>|밑을 10으로 사용하여 지정된 숫자의 로그를 반환합니다.|
|<xref:System.Math.Max%2A>|두 숫자 중 더 큰 숫자를 반환 합니다.|
|<xref:System.Math.Min%2A>|두 개의 숫자 중 더 작은 숫자를 반환합니다.|
|<xref:System.Math.Pow%2A>|지정된 숫자의 지정된 거듭제곱을 반환합니다.|
|<xref:System.Math.Round%2A>|`Decimal` `Double` 가장 가까운 정수 값 또는 지정 된 소수 자릿수로 반올림 된 또는 값을 반환 합니다.|
|<xref:System.Math.Sign%2A>|`Integer`숫자의 부호를 나타내는 값을 반환 합니다.|
|<xref:System.Math.Sin%2A>|지정된 각도의 사인을 반환합니다.|
|<xref:System.Math.Sinh%2A>|지정된 각도의 하이퍼볼릭 사인을 반환합니다.|
|<xref:System.Math.Sqrt%2A>|지정된 숫자의 제곱근을 반환합니다.|
|<xref:System.Math.Tan%2A>|지정된 각도의 탄젠트를 반환합니다.|
|<xref:System.Math.Tanh%2A>|지정된 각도의 하이퍼볼릭 탄젠트를 반환합니다.|
|<xref:System.Math.Truncate%2A>|지정 된 또는 숫자의 정수 부분을 계산 `Decimal` `Double` 합니다.|

다음 표에서는 <xref:System.Math?displayProperty=nameWithType> .NET Framework에는 없지만 .NET Standard 또는 .Net Core에 추가 된 클래스의 메서드를 보여 줍니다.

|.NET 메서드|설명|에서 사용 가능|
|---------------------------|-----------------|-----------|
|<xref:System.Math.Acosh%2A>|쌍곡선 코사인을 적용했을 때 지정된 숫자가 나오는 각도를 반환합니다.|.NET Core 2.1 및 .NET Standard 2.1부터 시작|
|<xref:System.Math.Asinh%2A>|쌍곡선 사인을 적용했을 때 지정된 숫자가 나오는 각도를 반환합니다.|.NET Core 2.1 및 .NET Standard 2.1부터 시작|
|<xref:System.Math.Atanh%2A>|쌍곡선 탄젠트를 적용했을 때 지정된 숫자가 나오는 각도를 반환합니다.|.NET Core 2.1 및 .NET Standard 2.1부터 시작|
|<xref:System.Math.BitDecrement%2A>|`x`보다 작은 값을 비교하여 다음으로 작은 값을 반환합니다.|.NET Core 3.0부터|
|<xref:System.Math.BitIncrement%2A>|`x`보다 큰 값을 비교하여 다음으로 큰 값을 반환합니다.|.NET Core 3.0부터|
|<xref:System.Math.Cbrt%2A>|지정된 숫자의 세제곱근을 반환합니다.|.NET Core 2.1 및 .NET Standard 2.1부터 시작|
|<xref:System.Math.Clamp%2A>|`min` 및 `max`의 포괄적인 범위에 고정되어 있는 `value`를 반환합니다.|.NET Core 2.0 및 .NET Standard 2.1부터 시작|
|<xref:System.Math.CopySign%2A>|`x`의 크기 및 `y`의 부호 값을 반환합니다.|.NET Core 3.0부터|
|<xref:System.Math.FusedMultiplyAdd%2A>|\*단일 삼항 연산으로 반올림 된 (x y) + z를 반환 합니다.|.NET Core 3.0부터|
|<xref:System.Math.ILogB%2A>|지정된 숫자의 기본 2 정수 로그를 반환합니다.|.NET Core 3.0부터|
|<xref:System.Math.Log2%2A>|밑을 2로 사용하여 지정된 숫자의 로그를 반환합니다.|.NET Core 3.0부터|
|<xref:System.Math.MaxMagnitude%2A>|두 개의 배정밀도 부동 소수점 수 중 더 큰 크기를 반환합니다.|.NET Core 3.0부터|
|<xref:System.Math.MinMagnitude%2A>|두 개의 배정밀도 부동 소수점 수 중 더 작은 크기를 반환합니다.|.NET Core 3.0부터|
|<xref:System.Math.ScaleB%2A>|는 \* 를 효율적으로 계산 하 여 x 2 ^ n을 반환 합니다.|.NET Core 3.0부터|

이러한 함수를 한정자 없이 사용 하려면 <xref:System.Math?displayProperty=nameWithType> 소스 파일의 맨 위에 다음 코드를 추가 하 여 네임 스페이스를 프로젝트로 가져옵니다.

```vb
Imports System.Math
```

## <a name="example---abs"></a>예-Abs

이 예제에서는 클래스의 메서드를 사용 하 여 <xref:System.Math.Abs%2A> <xref:System.Math> 숫자의 절대값을 계산 합니다.

```vb
Dim x As Double = Math.Abs(50.3)
Dim y As Double = Math.Abs(-50.3)
Console.WriteLine(x)
Console.WriteLine(y)
' This example produces the following output:
' 50.3
' 50.3
```  

## <a name="example---atan"></a>예제-Atan

이 예제에서는 클래스의 메서드를 사용 하 여 <xref:System.Math.Atan%2A> <xref:System.Math> pi 값을 계산 합니다.

```vb
Public Function GetPi() As Double
    ' Calculate the value of pi.
    Return 4.0 * Math.Atan(1.0)
End Function
```

> [!NOTE]
> <xref:System.Math?displayProperty=nameWithType>클래스는 상수 필드를 포함 합니다 <xref:System.Math.PI?displayProperty=nameWithType> . 이를 계산 하는 대신 사용할 수 있습니다.

## <a name="example---cos"></a>예-Cos

이 예제에서는 클래스의 메서드를 사용 하 여 <xref:System.Math.Cos%2A> <xref:System.Math> 각도의 코사인을 반환 합니다.

```vb
Public Function Sec(angle As Double) As Double
    ' Calculate the secant of angle, in radians.
    Return 1.0 / Math.Cos(angle)
End Function
```

## <a name="example---exp"></a>예제-Exp

이 예제에서는 클래스의 메서드를 사용 하 여 <xref:System.Math.Exp%2A> <xref:System.Math> e의 거듭제곱을 반환 합니다.

```vb
Public Function Sinh(angle As Double) As Double
    ' Calculate hyperbolic sine of an angle, in radians.
    Return (Math.Exp(angle) - Math.Exp(-angle)) / 2.0
End Function
```

## <a name="example---log"></a>예-로그

이 예제에서는 클래스의 메서드를 사용 하 여 <xref:System.Math.Log%2A> <xref:System.Math> 숫자의 자연 로그를 반환 합니다.

```vb
Public Function Asinh(value As Double) As Double
    ' Calculate inverse hyperbolic sine, in radians.
    Return Math.Log(value + Math.Sqrt(value * value + 1.0))
End Function
```

## <a name="example---round"></a>예제-Round

이 예제에서는 클래스의 메서드를 사용 하 여 <xref:System.Math.Round%2A> <xref:System.Math> 숫자를 가장 가까운 정수로 반올림 합니다.

```vb
Dim myVar2 As Double = Math.Round(2.8)
Console.WriteLine(myVar2)
' The code produces the following output:
' 3
```

## <a name="example---sign"></a>예제-서명

이 예제에서는 클래스의 메서드를 사용 하 여 <xref:System.Math.Sign%2A> <xref:System.Math> 숫자의 부호를 확인 합니다.

```vb
Dim mySign1 As Integer = Math.Sign(12)
Dim mySign2 As Integer = Math.Sign(-2.4)
Dim mySign3 As Integer = Math.Sign(0)
Console.WriteLine(mySign1)
Console.WriteLine(mySign2)
Console.WriteLine(mySign3)
' The code produces the following output:
' 1
' -1
' 0
```

## <a name="example---sin"></a>예-Sin

이 예제에서는 클래스의 메서드를 사용 하 여 <xref:System.Math.Sin%2A> <xref:System.Math> 각도의 사인을 반환 합니다.

```vb
Public Function Csc(angle As Double) As Double
    ' Calculate cosecant of an angle, in radians.
    Return 1.0 / Math.Sin(angle)
End Function
```

## <a name="example---sqrt"></a>예-Sqrt

이 예제에서는 클래스의 메서드를 사용 하 여 <xref:System.Math.Sqrt%2A> <xref:System.Math> 숫자의 제곱근을 계산 합니다.

```vb
Dim mySqrt1 As Double = Math.Sqrt(4)
Dim mySqrt2 As Double = Math.Sqrt(23)
Dim mySqrt3 As Double = Math.Sqrt(0)
Dim mySqrt4 As Double = Math.Sqrt(-4)
Console.WriteLine(mySqrt1)
Console.WriteLine(mySqrt2)
Console.WriteLine(mySqrt3)
Console.WriteLine(mySqrt4)
' The code produces the following output:
' 2
' 4.79583152331272
' 0
' NaN
```

## <a name="example---tan"></a>예-황갈색

이 예제에서는 클래스의 메서드를 사용 하 여 <xref:System.Math.Tan%2A> <xref:System.Math> 각도의 탄젠트를 반환 합니다.

```vb
Public Function Ctan(angle As Double) As Double
    ' Calculate cotangent of an angle, in radians.
    Return 1.0 / Math.Tan(angle)
End Function
```

## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.VBMath.Rnd%2A>
- <xref:Microsoft.VisualBasic.VBMath.Randomize%2A>
- <xref:System.Double.NaN>
- [파생된 수학 함수](../keywords/derived-math-functions.md)
- [산술 연산자](../operators/arithmetic-operators.md)
