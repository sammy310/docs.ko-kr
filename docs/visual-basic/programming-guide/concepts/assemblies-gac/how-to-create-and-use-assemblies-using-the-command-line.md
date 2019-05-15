---
title: '방법: 명령줄 (Visual Basic)를 사용 하 여 어셈블리 만들기 및 사용'
ms.date: 03/14/2018
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
ms.openlocfilehash: a30d4b3ea203a8b4d3ba621fc7b0310477ddf10d
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592691"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a>방법: 명령줄 (Visual Basic)를 사용 하 여 어셈블리 만들기 및 사용
어셈블리 또는 DLL(동적 연결 라이브러리)은 런타임 시 프로그램에 연결됩니다. DLL 빌드 및 사용을 보여 주려면 다음 시나리오를 고려합니다.  
  
- `MathLibrary.DLL`: 런타임 시 호출할 메서드가 포함된 라이브러리 파일입니다. 이 예제의 DLL에는 두 개의 메서드 `Add` 및 `Multiply`가 포함되어 있습니다.  
  
- `Add`: `Add` 메서드가 포함된 원본 파일입니다. 해당 매개 변수의 합계를 반환합니다. `Add` 메서드가 포함된 `AddClass` 클래스는 `UtilityMethods` 네임스페이스의 멤버입니다.  
  
- `Mult`: `Multiply` 메서드가 포함된 소스 코드입니다. 매개 변수의 곱을 반환합니다. `Multiply` 메서드가 포함된 `MultiplyClass` 클래스는 `UtilityMethods` 네임스페이스의 멤버이기도 합니다.  
  
- `TestCode`: `Main` 메서드가 포함된 파일입니다. DLL 파일의 메서드를 사용하여 런타임 인수의 합계와 곱을 계산합니다.  
  
## <a name="example"></a>예제  
  
```vb  
' File: Add.vb   
Namespace UtilityMethods  
    Public Class AddClass  
        Public Shared Function Add(ByVal i As Long, ByVal j As Long) As Long  
            Return i + j  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: Mult.vb  
Namespace UtilityMethods  
    Public Class MultiplyClass  
        Public Shared Function Multiply(ByVal x As Long, ByVal y As Long) As Long  
            Return x * y  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: TestCode.vb  
  
Imports UtilityMethods  
  
Module Test  
  
    Sub Main(ByVal args As String())  
  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:")  
  
        If args.Length <> 2 Then  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>")  
            Return  
        End If  
  
        Dim num1 As Long = Long.Parse(args(0))  
        Dim num2 As Long = Long.Parse(args(1))  
  
        Dim sum As Long = AddClass.Add(num1, num2)  
        Dim product As Long = MultiplyClass.Multiply(num1, num2)  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum)  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product)  
  
    End Sub  
  
End Module  
  
' Output (assuming 1234 and 5678 are entered as command-line arguments):  
' Calling methods from MathLibrary.DLL:  
' 1234 + 5678 = 6912  
' 1234 * 5678 = 7006652  
```  
  
 이 파일에는 DLL 메서드 `Add` 및 `Multiply`를 사용하는 알고리즘이 포함되어 있습니다. 명령줄에서 입력된 인수 `num1` 및 `num2`의 구문 분석으로 시작합니다. 그런 다음 `AddClass` 클래스의 `Add` 메서드를 사용하여 합계를 계산하고 `MultiplyClass` 클래스의 `Multiply` 메서드를 사용하여 곱을 계산합니다.  
  
 에 `Imports` 파일의 시작 부분에 문을 사용 하면 정규화 되지 않은 클래스 이름을 사용 하 여 컴파일 시간에 DLL 메서드를 다음과 같이 참조할 수 있습니다.  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 사용하지 않을 경우 정규화된 이름을 다음과 같이 사용해야 합니다.  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a>실행  
 프로그램을 실행하려면 다음과 같이 EXE 파일의 이름과 두 개의 숫자를 차례로 입력합니다.  
  
 `TestCode 1234 5678`  
  
## <a name="see-also"></a>참고자료

- [프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md)
- [.NET 어셈블리](../../../../standard/assembly/index.md)
- [DLL 함수가 포함된 클래스 만들기](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
