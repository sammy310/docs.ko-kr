---
title: '방법: 명령줄을 사용하여 어셈블리 만들기 및 사용(C#)'
ms.date: 07/20/2015
ms.assetid: 408ddce3-89e3-4e12-8353-34a49beeb72b
ms.openlocfilehash: 0a8db22a05d834d15f6e6b7f049f59f86bc1fe1d
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595970"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a>방법: 명령줄을 사용하여 어셈블리 만들기 및 사용(C#)
어셈블리 또는 DLL(동적 연결 라이브러리)은 런타임 시 프로그램에 연결됩니다. DLL 빌드 및 사용을 보여 주려면 다음 시나리오를 고려합니다.  
  
- `MathLibrary.DLL`: 런타임 시 호출할 메서드가 포함된 라이브러리 파일입니다. 이 예제의 DLL에는 두 개의 메서드 `Add` 및 `Multiply`가 포함되어 있습니다.  
  
- `Add`: `Add` 메서드가 포함된 원본 파일입니다. 해당 매개 변수의 합계를 반환합니다. `Add` 메서드가 포함된 `AddClass` 클래스는 `UtilityMethods` 네임스페이스의 멤버입니다.  
  
- `Mult`: `Multiply` 메서드가 포함된 소스 코드입니다. 매개 변수의 곱을 반환합니다. `Multiply` 메서드가 포함된 `MultiplyClass` 클래스는 `UtilityMethods` 네임스페이스의 멤버이기도 합니다.  
  
- `TestCode`: `Main` 메서드가 포함된 파일입니다. DLL 파일의 메서드를 사용하여 런타임 인수의 합계와 곱을 계산합니다.  
  
## <a name="example"></a>예  
  
```csharp  
// File: Add.cs   
namespace UtilityMethods  
{  
    public class AddClass   
    {  
        public static long Add(long i, long j)   
        {   
            return (i + j);  
        }  
    }  
}  
```  
  
```csharp  
// File: Mult.cs  
namespace UtilityMethods   
{  
    public class MultiplyClass  
    {  
        public static long Multiply(long x, long y)   
        {  
            return (x * y);   
        }  
    }  
}  
```  
  
```csharp  
// File: TestCode.cs  
  
using UtilityMethods;  
  
class TestCode  
{  
    static void Main(string[] args)   
    {  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:");  
  
        if (args.Length != 2)  
        {  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>");  
            return;  
        }  
  
        long num1 = long.Parse(args[0]);  
        long num2 = long.Parse(args[1]);  
  
        long sum = AddClass.Add(num1, num2);  
        long product = MultiplyClass.Multiply(num1, num2);  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum);  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product);  
    }  
}  
/* Output (assuming 1234 and 5678 are entered as command-line arguments):  
    Calling methods from MathLibrary.DLL:  
    1234 + 5678 = 6912  
    1234 * 5678 = 7006652          
*/  
```  
  
 이 파일에는 DLL 메서드 `Add` 및 `Multiply`를 사용하는 알고리즘이 포함되어 있습니다. 명령줄에서 입력된 인수 `num1` 및 `num2`의 구문 분석으로 시작합니다. 그런 다음 `AddClass` 클래스의 `Add` 메서드를 사용하여 합계를 계산하고 `MultiplyClass` 클래스의 `Multiply` 메서드를 사용하여 곱을 계산합니다.  
  
 파일의 시작 부분에 `using` 지시문을 사용하면 정규화되지 않은 클래스 이름을 통해 컴파일 시간에 DLL 메서드를 다음과 같이 참조할 수 있습니다.  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 사용하지 않을 경우 정규화된 이름을 다음과 같이 사용해야 합니다.  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a>실행  
 프로그램을 실행하려면 다음과 같이 EXE 파일의 이름과 두 개의 숫자를 차례로 입력합니다.  
  
 `TestCode 1234 5678`  
  
## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../../index.md)
- [.NET 어셈블리](../../../../standard/assembly/index.md)
- [DLL 함수가 포함된 클래스 만들기](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
