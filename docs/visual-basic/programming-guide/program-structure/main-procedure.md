---
title: Visual Basic의 Main 프로시저
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: a1eebc3d384d2efef050672a9c589b14559977f5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648761"
---
# <a name="main-procedure-in-visual-basic"></a>Visual Basic의 Main 프로시저
모든 Visual Basic 응용 프로그램 라는 프로시저에 있어야 합니다. `Main`합니다. 이 절차에는 시작 지점 및 응용 프로그램에 대 한 전체 제어 하는 대로 사용 됩니다. .NET Framework 호출 프로그램 `Main` 프로시저 응용 프로그램 로드 시 컨트롤 전달할 준비가 되었습니다. 작성 해야 합니다는 Windows Forms 응용 프로그램을 만들 경우를 제외 합니다 `Main` 자체적으로 실행 하는 응용 프로그램에 대 한 절차입니다.  
  
 `Main` 첫 번째 실행 되는 코드를 포함 합니다. `Main`, 프로그램을 시작할 때 먼저 로드할 형태 인지, 응용 프로그램의 복사본은 시스템에서 이미 실행 중 확인, 응용 프로그램에 대 한 일련의 변수를 설정 하거나 응용 프로그램에 필요한 데이터베이스를 열 수 있습니다.  
  
## <a name="requirements-for-the-main-procedure"></a>Main 프로시저에 대 한 요구 사항  
 자체 (일반적으로 확장명이.exe)을 실행 하는 파일을 포함 해야 합니다는 `Main` 프로시저입니다. 라이브러리 (예를 들어 확장명.dll)에서 실행할 수 없습니다 자체 및 필요 하지 않습니다는 `Main` 프로시저입니다. 다양 한 유형의 프로젝트에 대 한 요구 사항을 만들면 아래와 같습니다.  
  
- 콘솔 응용 프로그램 자체를 실행 하 고 하나 이상 제공 해야 `Main` 프로시저입니다. .  
  
- Windows Forms 응용 프로그램을 자체적으로 실행 합니다. 그러나 Visual Basic 컴파일러를 자동으로 생성을 `Main` 이러한 프로시저는 응용 프로그램에 않아도 작성 합니다.  
  
- 클래스 라이브러리는 필요 하지 않습니다는 `Main` 프로시저입니다. 이러한 Windows 컨트롤 라이브러리 및 웹 컨트롤 라이브러리를 포함 합니다. 웹 응용 프로그램 클래스 라이브러리로 배포 됩니다.  
  
## <a name="declaring-the-main-procedure"></a>기본 프로시저를 선언합니다.  
 선언 하는 방법은 네 가지는 `Main` 프로시저입니다. 인수 걸릴 수 있습니다 및 여부 값을 반환할 수 있습니다.  
  
> [!NOTE]
>  선언 하는 경우 `Main` 클래스를 사용 해야 하는 `Shared` 키워드입니다. 모듈의 `Main` 될 필요가 없습니다 `Shared`합니다.  
  
- 가장 간단한 방법은 선언 하는 것을 `Sub` 인수를 사용 하지 않거나 값을 반환 하는 프로시저입니다.  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
- `Main` 반환할 수도 있습니다는 `Integer` 운영 체제에서 프로그램에 대 한 종료 코드로 사용 하는 값입니다. 다른 프로그램 Windows ERRORLEVEL 값을 검사 하 여이 코드를 테스트할 수 있습니다. 종료 코드 반환을 선언 해야 합니다 `Main` 으로 `Function` 대신 프로시저는 `Sub` 프로시저입니다.  
  
    ```  
    Module mainModule  
        Function Main() As Integer  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' Insert call to appropriate starting place in your code.  
            ' On return, assign appropriate value to returnValue.  
            ' 0 usually means successful completion.  
            MsgBox("The application is terminating with error level " &  
                 CStr(returnValue) & ".")  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
- `Main` 또한 수는 `String` 배열을 인수로 합니다. 배열의 각 문자열에 프로그램을 호출 하는 데 명령줄 인수 중 하나가 포함 됩니다. 해당 값에 따라 다른 작업을 수행할 수 있습니다.  
  
    ```  
    Module mainModule  
        Function Main(ByVal cmdArgs() As String) As Integer  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' See if there are any arguments.  
            If cmdArgs.Length > 0 Then  
                For argNum As Integer = 0 To UBound(cmdArgs, 1)  
                    ' Insert code to examine cmdArgs(argNum) and take  
                    ' appropriate action based on its value.  
                Next argNum  
            End If  
            ' Insert call to appropriate starting place in your code.  
            ' On return, assign appropriate value to returnValue.  
            ' 0 usually means successful completion.  
            MsgBox("The application is terminating with error level " &  
                 CStr(returnValue) & ".")  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
- 선언할 수 있습니다 `Main` 명령줄 인수를 검사 하지만 하지는 종료 코드를 다음과 같이 반환 합니다.  
  
    ```  
    Module mainModule  
        Sub Main(ByVal cmdArgs() As String)  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' See if there are any arguments.  
            If cmdArgs.Length > 0 Then  
                For argNum As Integer = 0 To UBound(cmdArgs, 1)  
                    ' Insert code to examine cmdArgs(argNum) and take  
                    ' appropriate action based on its value.  
                Next argNum  
            End If  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [Visual Basic 프로그램의 구조](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [/main](../../../visual-basic/reference/command-line-compiler/main.md)
- [공유](../../../visual-basic/language-reference/modifiers/shared.md)
- [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)
- [Integer 데이터 형식](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [String 데이터 형식](../../../visual-basic/language-reference/data-types/string-data-type.md)
