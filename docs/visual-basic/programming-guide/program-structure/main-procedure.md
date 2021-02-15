---
description: '에 대 한 자세한 정보: 주 프로시저 Visual Basic'
title: 기본 절차
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: b25190ef216fe4219923a27d6bbe0acff4536685
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432808"
---
# <a name="main-procedure-in-visual-basic"></a>Visual Basic의 Main 프로시저

모든 Visual Basic 응용 프로그램은 라는 프로시저를 포함 해야 합니다 `Main` . 이 절차는 응용 프로그램에 대 한 시작 지점 및 전반적인 제어 역할을 합니다. .NET Framework는 `Main` 응용 프로그램을 로드 하 고 제어를 전달할 준비가 되었을 때 프로시저를 호출 합니다. Windows Forms 응용 프로그램을 만드는 경우를 제외 하 고 자체적으로 `Main` 실행 되는 응용 프로그램에 대 한 프로시저를 작성 해야 합니다.

 `Main` 먼저 실행 되는 코드를 포함 합니다. 에서는 `Main` 프로그램이 시작 될 때 먼저 로드 되는 폼을 확인 하 고, 응용 프로그램의 복사본이 이미 시스템에서 실행 되 고 있는지 확인 하 고, 응용 프로그램에 대 한 변수 집합을 설정 하거나, 응용 프로그램에 필요한 데이터베이스를 열 수 있습니다.

## <a name="requirements-for-the-main-procedure"></a>주 절차에 대 한 요구 사항

 자체 (일반적으로 확장명 .exe)에서 실행 되는 파일은 프로시저를 포함 해야 합니다 `Main` . 라이브러리 (예: 확장명 .dll)는 자체에서 실행 되지 않으며 프로시저가 필요 하지 않습니다 `Main` . 만들 수 있는 다양 한 프로젝트 형식에 대 한 요구 사항은 다음과 같습니다.

- 콘솔 응용 프로그램은 자체적으로 실행 되며 하나 이상의 프로시저를 제공 해야 합니다 `Main` .

- Windows Forms 응용 프로그램은 자체적으로 실행 됩니다. 그러나 Visual Basic 컴파일러는 `Main` 이러한 응용 프로그램에서 프로시저를 자동으로 생성 하므로 작성 하지 않아도 됩니다.

- 클래스 라이브러리에는 프로시저가 필요 하지 않습니다 `Main` . 여기에는 Windows 컨트롤 라이브러리 및 웹 컨트롤 라이브러리가 포함 됩니다. 웹 응용 프로그램은 클래스 라이브러리로 배포 됩니다.

## <a name="declaring-the-main-procedure"></a>Main 프로시저 선언

 프로시저를 선언 하는 방법에는 네 가지가 있습니다 `Main` . 인수를 사용할 수 있으며 값을 반환할 수 있습니다.

> [!NOTE]
> 클래스에서를 선언 하는 경우 `Main` 키워드를 사용 해야 합니다 `Shared` . 모듈에서는 `Main` 일 필요가 없습니다 `Shared` .

- 가장 간단한 방법은 `Sub` 인수를 사용 하지 않거나 값을 반환 하지 않는 프로시저를 선언 하는 것입니다.

    ```vb
    Module mainModule
        Sub Main()
            MsgBox("The Main procedure is starting the application.")
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```

- `Main` 는 `Integer` 운영 체제에서 프로그램의 종료 코드로 사용 하는 값을 반환할 수도 있습니다. 다른 프로그램은 Windows ERRORLEVEL 값을 검사 하 여이 코드를 테스트할 수 있습니다. 종료 코드를 반환 하려면를 프로시저 대신 프로시저로 선언 해야 합니다 `Main` `Function` `Sub` .

    ```vb
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

- `Main` 는 배열을 인수로 사용할 수도 있습니다 `String` . 배열의 각 문자열은 프로그램을 호출 하는 데 사용 되는 명령줄 인수 중 하나를 포함 합니다. 값에 따라 다른 작업을 수행할 수 있습니다.

    ```vb
    Module mainModule
        Function Main(ByVal cmdArgs() As String) As Integer
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
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

- `Main`다음과 같이 명령줄 인수를 검사 하지만 종료 코드를 반환 하지 않도록 선언할 수 있습니다.

    ```vb
    Module mainModule
        Sub Main(ByVal cmdArgs() As String)
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
            End If
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```
  
## <a name="see-also"></a>추가 정보

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [Visual Basic 프로그램의 구조](structure-of-a-visual-basic-program.md)
- [-main](../../reference/command-line-compiler/main.md)
- [공유](../../language-reference/modifiers/shared.md)
- [Sub 문](../../language-reference/statements/sub-statement.md)
- [Function 문](../../language-reference/statements/function-statement.md)
- [Integer 데이터 형식](../../language-reference/data-types/integer-data-type.md)
- [문자열 데이터 형식](../../language-reference/data-types/string-data-type.md)
