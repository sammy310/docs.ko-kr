---
title: '방법: 부호 없는 형식을 사용하는 Windows 함수 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- Windows functions [Visual Basic], calling
- unsigned data types [Visual Basic]
- UShort data type [Visual Basic], using
- functions [Visual Basic], calling Windows functions
- ULong data type [Visual Basic], using
- UInteger data type [Visual Basic], using
- data types [Visual Basic], using
- unsigned types [Visual Basic]
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types [Visual Basic], using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
ms.openlocfilehash: 5b78c808de4a16060d37844ad0f17e89fa6f6d84
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548080"
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a><span data-ttu-id="4bea2-102">방법: 부호 없는 형식을 사용하는 Windows 함수 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4bea2-102">How to: Call a Windows Function that Takes Unsigned Types (Visual Basic)</span></span>

<span data-ttu-id="4bea2-103">부호 없는 정수 형식의 멤버를 포함 하는 클래스, 모듈 또는 구조체를 사용 하는 경우 Visual Basic를 사용 하 여 이러한 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bea2-103">If you are consuming a class, module, or structure that has members of unsigned integer types, you can access these members with Visual Basic.</span></span>

## <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a><span data-ttu-id="4bea2-104">부호 없는 형식을 사용 하는 Windows 함수를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="4bea2-104">To call a Windows function that takes an unsigned type</span></span>

1. <span data-ttu-id="4bea2-105">[Declare 문을](../../language-reference/statements/declare-statement.md) 사용 하 여 함수를 포함 하는 라이브러리, 해당 라이브러리에 있는 이름, 호출 하는 시퀀스의 정의, 호출 시 문자열을 변환 하는 방법에 대 한 Visual Basic를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4bea2-105">Use a [Declare Statement](../../language-reference/statements/declare-statement.md) to tell Visual Basic which library holds the function, what its name is in that library, what its calling sequence is, and how to convert strings when calling it.</span></span>

2. <span data-ttu-id="4bea2-106">문에서는 `Declare` `UInteger` ,, 또는를 `ULong` `UShort` `Byte` 부호 없는 형식의 각 매개 변수에 적합 하 게 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bea2-106">In the `Declare` statement, use `UInteger`, `ULong`, `UShort`, or `Byte` as appropriate for each parameter with an unsigned type.</span></span>

3. <span data-ttu-id="4bea2-107">호출 하는 Windows 함수 설명서를 참조 하 여 사용 하는 상수의 이름과 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bea2-107">Consult the documentation for the Windows function you are calling to find the names and values of the constants it uses.</span></span> <span data-ttu-id="4bea2-108">이러한 중 상당수는 Winuser.h 파일에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bea2-108">Many of these are defined in the WinUser.h file.</span></span>

4. <span data-ttu-id="4bea2-109">코드에서 필요한 상수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bea2-109">Declare the necessary constants in your code.</span></span> <span data-ttu-id="4bea2-110">많은 Windows 상수는 32 비트 부호 없는 값 이며, 이러한 값을 선언 해야 `As UInteger` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bea2-110">Many Windows constants are 32-bit unsigned values, and you should declare these `As UInteger`.</span></span>

5. <span data-ttu-id="4bea2-111">일반적인 방법으로 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bea2-111">Call the function in the normal way.</span></span> <span data-ttu-id="4bea2-112">다음 예제에서는 `MessageBox` 부호 없는 정수 인수를 사용 하는 Windows 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bea2-112">The following example calls the Windows function `MessageBox`, which takes an unsigned integer argument.</span></span>

    ```vb
    Public Class windowsMessage
        Private Declare Auto Function mb Lib "user32.dll" Alias "MessageBox" (
            ByVal hWnd As Integer,
            ByVal lpText As String,
            ByVal lpCaption As String,
            ByVal uType As UInteger) As Integer
        Private Const MB_OK As UInteger = 0
        Private Const MB_ICONEXCLAMATION As UInteger = &H30
        Private Const IDOK As UInteger = 1
        Private Const IDCLOSE As UInteger = 8
        Private Const c As UInteger = MB_OK Or MB_ICONEXCLAMATION
        Public Function messageThroughWindows() As String
            Dim r As Integer = mb(0, "Click OK if you see this!",
                "Windows API call", c)
            Dim s As String = "Windows API MessageBox returned " &
                 CStr(r)& vbCrLf & "(IDOK = " & CStr(IDOK) &
                 ", IDCLOSE = " & CStr(IDCLOSE) & ")"
            Return s
        End Function
    End Class
    ```

     <span data-ttu-id="4bea2-113">다음 코드를 사용 하 여 함수를 테스트할 수 있습니다 `messageThroughWindows` .</span><span class="sxs-lookup"><span data-stu-id="4bea2-113">You can test the function `messageThroughWindows` with the following code.</span></span>

    ```vb
    Public Sub consumeWindowsMessage()
        Dim w As New windowsMessage
        w.messageThroughWindows()
    End Sub
    ```

    > [!CAUTION]
    > <span data-ttu-id="4bea2-114">`UInteger`,, `ULong` `UShort` 및 `SByte` 데이터 형식은 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (cls)의 일부가 아니므로 cls 규격 코드는이를 사용 하는 구성 요소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bea2-114">The `UInteger`, `ULong`, `UShort`, and `SByte` data types are not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot consume a component that uses them.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4bea2-115">Windows API (응용 프로그래밍 인터페이스)와 같은 비관리 코드에 대 한 호출을 수행 하면 잠재적인 보안 위험에 대 한 코드를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bea2-115">Making a call to unmanaged code, such as the Windows application programming interface (API), exposes your code to potential security risks.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4bea2-116">Windows API를 호출 하려면 부분 신뢰 상황에서 실행에 영향을 줄 수 있는 비관리 코드 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bea2-116">Calling the Windows API requires unmanaged code permission, which might affect its execution in partial-trust situations.</span></span> <span data-ttu-id="4bea2-117">자세한 내용은 <xref:System.Security.Permissions.SecurityPermission> 및 [코드 액세스 권한](/previous-versions/dotnet/netframework-4.0/h846e9b3(v=vs.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4bea2-117">For more information, see <xref:System.Security.Permissions.SecurityPermission> and [Code Access Permissions](/previous-versions/dotnet/netframework-4.0/h846e9b3(v=vs.100)).</span></span>

## <a name="see-also"></a><span data-ttu-id="4bea2-118">참조</span><span class="sxs-lookup"><span data-stu-id="4bea2-118">See also</span></span>

- [<span data-ttu-id="4bea2-119">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4bea2-119">Data Types</span></span>](../../language-reference/data-types/index.md)
- [<span data-ttu-id="4bea2-120">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4bea2-120">Integer Data Type</span></span>](../../language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="4bea2-121">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4bea2-121">UInteger Data Type</span></span>](../../language-reference/data-types/uinteger-data-type.md)
- [<span data-ttu-id="4bea2-122">Declare 문</span><span class="sxs-lookup"><span data-stu-id="4bea2-122">Declare Statement</span></span>](../../language-reference/statements/declare-statement.md)
- [<span data-ttu-id="4bea2-123">연습: Windows API 호출</span><span class="sxs-lookup"><span data-stu-id="4bea2-123">Walkthrough: Calling Windows APIs</span></span>](walkthrough-calling-windows-apis.md)
