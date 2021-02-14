---
description: '자세한 정보: 연습: Windows Api 호출 (Visual Basic)'
title: '연습: Windows API 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- DLLs, calling
- Windows API, walkthroughs
- platform invoke, walkthroughs
- API calls [Visual Basic], walkthroughs [Visual Basic]
- Windows API, calling
- walkthroughs [Visual Basic], API calls
- DllImport attribute, calling Windows API
- Declare statement [Visual Basic], declaring DLL functions
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
ms.openlocfilehash: 9ffe89cabade780dbe1ced189a92c37e822c59e9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100427260"
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a><span data-ttu-id="749dd-103">연습: Windows API 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="749dd-103">Walkthrough: Calling Windows APIs (Visual Basic)</span></span>

<span data-ttu-id="749dd-104">Windows Api는 Windows 운영 체제의 일부인 Dll (동적 연결 라이브러리)입니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-104">Windows APIs are dynamic-link libraries (DLLs) that are part of the Windows operating system.</span></span> <span data-ttu-id="749dd-105">이러한 작업을 사용 하 여 고유한 프로시저를 작성 하기가 어려울 때 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-105">You use them to perform tasks when it is difficult to write equivalent procedures of your own.</span></span> <span data-ttu-id="749dd-106">예를 들어 Windows는 `FlashWindowEx` 응용 프로그램에 대 한 제목 표시줄을 밝은 색과 어두운 음영 사이에서 교대로 수행할 수 있는 라는 함수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-106">For example, Windows provides a function named `FlashWindowEx` that lets you make the title bar for an application alternate between light and dark shades.</span></span>  
  
 <span data-ttu-id="749dd-107">코드에서 Windows Api를 사용 하는 이점은 이미 작성 되어 사용 대기 중인 수십 개의 유용한 함수를 포함 하기 때문에 개발 시간을 절약할 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-107">The advantage of using Windows APIs in your code is that they can save development time because they contain dozens of useful functions that are already written and waiting to be used.</span></span> <span data-ttu-id="749dd-108">단점은 Windows Api를 사용 하는 것이 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-108">The disadvantage is that Windows APIs can be difficult to work with and unforgiving when things go wrong.</span></span>  
  
 <span data-ttu-id="749dd-109">Windows Api는 특별 한 종류의 상호 운용성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-109">Windows APIs represent a special category of interoperability.</span></span> <span data-ttu-id="749dd-110">Windows Api는 관리 코드를 사용 하지 않고, 기본 제공 형식 라이브러리를 사용 하지 않으며, Visual Studio에서 사용 되는 것과 다른 데이터 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-110">Windows APIs do not use managed code, do not have built-in type libraries, and use data types that are different than those used with Visual Studio.</span></span> <span data-ttu-id="749dd-111">이러한 차이로 인해 Windows Api는 COM 개체가 아니기 때문에 Windows Api와의 상호 운용성 및 .NET Framework는 플랫폼 호출 또는 PInvoke를 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-111">Because of these differences, and because Windows APIs are not COM objects, interoperability with Windows APIs and the .NET Framework is performed using platform invoke, or PInvoke.</span></span> <span data-ttu-id="749dd-112">플랫폼 호출은 관리 코드에서 Dll에 구현 된 관리 되지 않는 함수를 호출할 수 있도록 하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-112">Platform invoke is a service that enables managed code to call unmanaged functions implemented in DLLs.</span></span> <span data-ttu-id="749dd-113">자세한 내용은 [관리 되지 않는 DLL 함수](../../../framework/interop/consuming-unmanaged-dll-functions.md)사용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="749dd-113">For more information, see [Consuming Unmanaged DLL Functions](../../../framework/interop/consuming-unmanaged-dll-functions.md).</span></span> <span data-ttu-id="749dd-114">`Declare`문을 사용 하거나 `DllImport` 빈 프로시저에 특성을 적용 하 여 Visual Basic에서 PInvoke를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-114">You can use PInvoke in Visual Basic by using either the `Declare` statement or applying the `DllImport` attribute to an empty procedure.</span></span>  
  
 <span data-ttu-id="749dd-115">Windows API 호출은 과거에 Visual Basic 프로그래밍의 중요 한 부분 이지만 Visual Basic .NET에서는 거의 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-115">Windows API calls were an important part of Visual Basic programming in the past, but are seldom necessary with Visual Basic .NET.</span></span> <span data-ttu-id="749dd-116">가능 하면 Windows API 호출 대신 .NET Framework에서 관리 코드를 사용 하 여 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-116">Whenever possible, you should use managed code from the .NET Framework to perform tasks, instead of Windows API calls.</span></span> <span data-ttu-id="749dd-117">이 연습에서는 Windows Api를 사용 해야 하는 상황에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-117">This walkthrough provides information for those situations in which using Windows APIs is necessary.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a><span data-ttu-id="749dd-118">선언을 사용 하 여 API 호출</span><span class="sxs-lookup"><span data-stu-id="749dd-118">API Calls Using Declare</span></span>  

 <span data-ttu-id="749dd-119">Windows Api를 호출 하는 가장 일반적인 방법은 문을 사용 하는 것입니다 `Declare` .</span><span class="sxs-lookup"><span data-stu-id="749dd-119">The most common way to call Windows APIs is by using the `Declare` statement.</span></span>  
  
### <a name="to-declare-a-dll-procedure"></a><span data-ttu-id="749dd-120">DLL 프로시저를 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="749dd-120">To declare a DLL procedure</span></span>  
  
1. <span data-ttu-id="749dd-121">호출 하려는 함수의 이름과 인수, 인수 형식 및 반환 값을 확인 하 고이를 포함 하는 DLL의 이름과 위치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-121">Determine the name of the function you want to call, plus its arguments, argument types, and return value, as well as the name and location of the DLL that contains it.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="749dd-122">Windows Api에 대 한 전체 정보는 Platform SDK Windows API에서 Win32 SDK 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="749dd-122">For complete information about the Windows APIs, see the Win32 SDK documentation in the Platform SDK Windows API.</span></span> <span data-ttu-id="749dd-123">Windows Api에서 사용 하는 상수에 대 한 자세한 내용은 Platform SDK에 포함 된 Windows 등의 헤더 파일을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-123">For more information about the constants that Windows APIs use, examine the header files such as Windows.h included with the Platform SDK.</span></span>  
  
2. <span data-ttu-id="749dd-124">**파일** 메뉴에서 **새로 만들기** 를 클릭 한 다음 **프로젝트** 를 클릭 하 여 새 Windows 응용 프로그램 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-124">Open a new Windows Application project by clicking **New** on the **File** menu, and then clicking **Project**.</span></span> <span data-ttu-id="749dd-125">**새 프로젝트** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-125">The **New Project** dialog box appears.</span></span>  
  
3. <span data-ttu-id="749dd-126">Visual Basic 프로젝트 템플릿 목록에서 **Windows 응용 프로그램** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-126">Select **Windows Application** from the list of Visual Basic project templates.</span></span> <span data-ttu-id="749dd-127">새 프로젝트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-127">The new project is displayed.</span></span>  
  
4. <span data-ttu-id="749dd-128">`Declare`DLL을 사용 하려는 클래스나 모듈에 다음 함수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-128">Add the following `Declare` function either to the class or module in which you want to use the DLL:</span></span>  
  
     [!code-vb[VbVbalrInterop#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#9)]  
  
### <a name="parts-of-the-declare-statement"></a><span data-ttu-id="749dd-129">Declare 문의 일부</span><span class="sxs-lookup"><span data-stu-id="749dd-129">Parts of the Declare Statement</span></span>  

 <span data-ttu-id="749dd-130">`Declare`문에는 다음과 같은 요소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-130">The `Declare` statement includes the following elements.</span></span>  
  
#### <a name="auto-modifier"></a><span data-ttu-id="749dd-131">Auto 한정자</span><span class="sxs-lookup"><span data-stu-id="749dd-131">Auto modifier</span></span>  

 <span data-ttu-id="749dd-132">`Auto`한정자는 공용 언어 런타임 규칙 또는 별칭 이름 (지정 된 경우)에 따라 메서드 이름에 따라 문자열을 변환 하도록 런타임에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-132">The `Auto` modifier instructs the runtime to convert the string based on the method name according to common language runtime rules (or alias name if specified).</span></span>  
  
#### <a name="lib-and-alias-keywords"></a><span data-ttu-id="749dd-133">Lib 및 Alias 키워드</span><span class="sxs-lookup"><span data-stu-id="749dd-133">Lib and Alias keywords</span></span>  

 <span data-ttu-id="749dd-134">키워드 뒤의 이름은 `Function` 프로그램에서 가져온 함수에 액세스 하는 데 사용 하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-134">The name following the `Function` keyword is the name your program uses to access the imported function.</span></span> <span data-ttu-id="749dd-135">호출 하는 함수의 실제 이름과 같을 수도 있고, 유효한 프로시저 이름을 사용 하 고 키워드를 사용 `Alias` 하 여 호출 하는 함수의 실제 이름을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-135">It can be the same as the real name of the function you are calling, or you can use any valid procedure name and then employ the `Alias` keyword to specify the real name of the function you are calling.</span></span>  
  
 <span data-ttu-id="749dd-136">`Lib`키워드를 지정 하 고 그 뒤에 호출 하는 함수가 포함 된 DLL의 이름과 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-136">Specify the `Lib` keyword, followed by the name and location of the DLL that contains the function you are calling.</span></span> <span data-ttu-id="749dd-137">Windows 시스템 디렉터리에 있는 파일에 대 한 경로를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-137">You do not need to specify the path for files located in the Windows system directories.</span></span>  
  
 <span data-ttu-id="749dd-138">`Alias`호출 하는 함수 이름이 올바른 Visual Basic 프로시저 이름이 아니거나 응용 프로그램의 다른 항목 이름과 충돌 하는 경우 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-138">Use the `Alias` keyword if the name of the function you are calling is not a valid Visual Basic procedure name, or conflicts with the name of other items in your application.</span></span> <span data-ttu-id="749dd-139">`Alias` 호출 되는 함수의 실제 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-139">`Alias` indicates the true name of the function being called.</span></span>  
  
#### <a name="argument-and-data-type-declarations"></a><span data-ttu-id="749dd-140">인수 및 데이터 형식 선언</span><span class="sxs-lookup"><span data-stu-id="749dd-140">Argument and Data Type Declarations</span></span>  

 <span data-ttu-id="749dd-141">인수와 해당 데이터 형식을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-141">Declare the arguments and their data types.</span></span> <span data-ttu-id="749dd-142">이 부분은 Windows에서 사용 하는 데이터 형식이 Visual Studio 데이터 형식과 일치 하지 않기 때문에 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-142">This part can be challenging because the data types that Windows uses do not correspond to Visual Studio data types.</span></span> <span data-ttu-id="749dd-143">Visual Basic는 인수를 호환 되는 데이터 형식으로 변환 하 여 *마샬링* 이라는 프로세스를 수행 하는 데 많은 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-143">Visual Basic does a lot of the work for you by converting arguments to compatible data types, a process called *marshaling*.</span></span> <span data-ttu-id="749dd-144"><xref:System.Runtime.InteropServices.MarshalAsAttribute>네임 스페이스에 정의 된 특성을 사용 하 여 인수가 마샬링되는 방식을 명시적으로 제어할 수 있습니다 <xref:System.Runtime.InteropServices> .</span><span class="sxs-lookup"><span data-stu-id="749dd-144">You can explicitly control how arguments are marshaled by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute defined in the <xref:System.Runtime.InteropServices> namespace.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="749dd-145">이전 버전의 Visual Basic을 사용 하 여 매개 변수를 선언할 수 있습니다 `As Any` . 즉, 모든 데이터 형식의 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-145">Previous versions of Visual Basic allowed you to declare parameters `As Any`, meaning that data of any data type could be used.</span></span> <span data-ttu-id="749dd-146">Visual Basic를 사용 하려면 모든 문에 특정 데이터 형식을 사용 해야 `Declare` 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-146">Visual Basic requires that you use a specific data type for all `Declare` statements.</span></span>  
  
#### <a name="windows-api-constants"></a><span data-ttu-id="749dd-147">Windows API 상수</span><span class="sxs-lookup"><span data-stu-id="749dd-147">Windows API Constants</span></span>  

 <span data-ttu-id="749dd-148">일부 인수는 상수의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-148">Some arguments are combinations of constants.</span></span> <span data-ttu-id="749dd-149">예를 들어 `MessageBox` 이 연습에 표시 된 API는 `Typ` 메시지 상자가 표시 되는 방식을 제어 하는 라는 정수 인수를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-149">For example, the `MessageBox` API shown in this walkthrough accepts an integer argument called `Typ` that controls how the message box is displayed.</span></span> <span data-ttu-id="749dd-150">이 상수는 `#define` winuser.h 파일의 문을 검사 하 여 숫자 값을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-150">You can determine the numeric value of these constants by examining the `#define` statements in the file WinUser.h.</span></span> <span data-ttu-id="749dd-151">숫자 값은 일반적으로 16 진수로 표시 되므로 계산기를 사용 하 여 숫자 값을 추가 하 고 decimal로 변환 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-151">The numeric values are generally shown in hexadecimal, so you may want to use a calculator to add them and convert to decimal.</span></span> <span data-ttu-id="749dd-152">예를 들어 느낌표 및 예/아니요 스타일 0x00000004에 대 한 상수를 결합 하려는 경우 `MB_ICONEXCLAMATION` `MB_YESNO` 숫자를 추가 하 고 0x00000030 또는 52 진수의 결과를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-152">For example, if you want to combine the constants for the exclamation style `MB_ICONEXCLAMATION` 0x00000030 and the Yes/No style `MB_YESNO` 0x00000004, you can add the numbers and get a result of 0x00000034, or 52 decimal.</span></span> <span data-ttu-id="749dd-153">Decimal 결과를 직접 사용할 수 있지만 이러한 값을 응용 프로그램에서 상수로 선언 하 고 연산자를 사용 하 여 결합 하는 것이 좋습니다 `Or` .</span><span class="sxs-lookup"><span data-stu-id="749dd-153">Although you can use the decimal result directly, it is better to declare these values as constants in your application and combine them using the `Or` operator.</span></span>  
  
##### <a name="to-declare-constants-for-windows-api-calls"></a><span data-ttu-id="749dd-154">Windows API 호출에 대 한 상수를 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="749dd-154">To declare constants for Windows API calls</span></span>  
  
1. <span data-ttu-id="749dd-155">호출 하는 Windows 함수에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="749dd-155">Consult the documentation for the Windows function you are calling.</span></span> <span data-ttu-id="749dd-156">이 상수에 사용 되는 상수의 이름과 이러한 상수에 대 한 숫자 값을 포함 하는 .h 파일의 이름을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-156">Determine the name of the constants it uses and the name of the .h file that contains the numeric values for these constants.</span></span>  
  
2. <span data-ttu-id="749dd-157">메모장과 같은 텍스트 편집기를 사용 하 여 헤더 (.h) 파일의 내용을 보고 사용 중인 상수와 연결 된 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-157">Use a text editor, such as Notepad, to view the contents of the header (.h) file, and find the values associated with the constants you are using.</span></span> <span data-ttu-id="749dd-158">예를 들어 API는 상수를 사용 하 여 `MessageBox` `MB_ICONQUESTION` 메시지 상자에 물음표를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-158">For example, the `MessageBox` API uses the constant `MB_ICONQUESTION` to show a question mark in the message box.</span></span> <span data-ttu-id="749dd-159">에 대 한 정의는 `MB_ICONQUESTION` winuser.h에 있으며 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-159">The definition for `MB_ICONQUESTION` is in WinUser.h and appears as follows:</span></span>  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3. <span data-ttu-id="749dd-160">`Const`이러한 상수를 응용 프로그램에서 사용할 수 있도록 클래스 또는 모듈에 해당 하는 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-160">Add equivalent `Const` statements to your class or module to make these constants available to your application.</span></span> <span data-ttu-id="749dd-161">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-161">For example:</span></span>  
  
     [!code-vb[VbVbalrInterop#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#11)]  
  
###### <a name="to-call-the-dll-procedure"></a><span data-ttu-id="749dd-162">DLL 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="749dd-162">To call the DLL procedure</span></span>  
  
1. <span data-ttu-id="749dd-163">이라는 단추를 `Button1` 프로젝트의 시작 폼에 추가한 다음 두 번 클릭 하 여 해당 코드를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-163">Add a button named `Button1` to the startup form for your project, and then double-click it to view its code.</span></span> <span data-ttu-id="749dd-164">단추에 대 한 이벤트 처리기가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-164">The event handler for the button is displayed.</span></span>  
  
2. <span data-ttu-id="749dd-165">`Click`추가 된 단추에 대 한 이벤트 처리기에 코드를 추가 하 여 프로시저를 호출 하 고 적절 한 인수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-165">Add code to the `Click` event handler for the button you added, to call the procedure and provide the appropriate arguments:</span></span>  
  
     [!code-vb[VbVbalrInterop#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#12)]  
  
3. <span data-ttu-id="749dd-166">F5 키를 눌러 프로젝트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-166">Run the project by pressing F5.</span></span> <span data-ttu-id="749dd-167">메시지 상자에 **예** 및 응답 **없음** 단추가 모두 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-167">The message box is displayed with both **Yes** and **No** response buttons.</span></span> <span data-ttu-id="749dd-168">하나를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-168">Click either one.</span></span>  
  
#### <a name="data-marshaling"></a><span data-ttu-id="749dd-169">데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="749dd-169">Data Marshaling</span></span>  

 <span data-ttu-id="749dd-170">Visual Basic는 Windows API 호출에 대 한 매개 변수 및 반환 값의 데이터 형식을 자동으로 변환 하지만, `MarshalAs` 특성을 사용 하 여 API에 필요한 관리 되지 않는 데이터 형식을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-170">Visual Basic automatically converts the data types of parameters and return values for Windows API calls, but you can use the `MarshalAs` attribute to explicitly specify unmanaged data types that an API expects.</span></span> <span data-ttu-id="749dd-171">Interop 마샬링에 대 한 자세한 내용은 [Interop 마샬링](../../../framework/interop/interop-marshaling.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="749dd-171">For more information about interop marshaling, see [Interop Marshaling](../../../framework/interop/interop-marshaling.md).</span></span>  
  
##### <a name="to-use-declare-and-marshalas-in-an-api-call"></a><span data-ttu-id="749dd-172">API 호출에서 Declare 및 MarshalAs를 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="749dd-172">To use Declare and MarshalAs in an API call</span></span>  
  
1. <span data-ttu-id="749dd-173">호출 하려는 함수의 이름 및 해당 인수, 데이터 형식 및 반환 값을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-173">Determine the name of the function you want to call, plus its arguments, data types, and return value.</span></span>  
  
2. <span data-ttu-id="749dd-174">특성에 대 한 액세스를 간소화 하려면 `MarshalAs` `Imports` 다음 예제와 같이 클래스 또는 모듈에 대 한 코드의 맨 위에 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-174">To simplify access to the `MarshalAs` attribute, add an `Imports` statement to the top of the code for the class or module, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
3. <span data-ttu-id="749dd-175">가져온 함수의 함수 프로토타입을 사용 하는 클래스 또는 모듈에 추가 하 고 `MarshalAs` 특성을 매개 변수 또는 반환 값에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-175">Add a function prototype for the imported function to the class or module you are using, and apply the `MarshalAs` attribute to the parameters or return value.</span></span> <span data-ttu-id="749dd-176">다음 예제에서는 형식을 예상 하는 API 호출이 `void*` 다음과 같이 마샬링됩니다 `AsAny` .</span><span class="sxs-lookup"><span data-stu-id="749dd-176">In the following example, an API call that expects the type `void*` is marshaled as `AsAny`:</span></span>  
  
     [!code-vb[VbVbalrInterop#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#14)]  
  
## <a name="api-calls-using-dllimport"></a><span data-ttu-id="749dd-177">DllImport를 사용 하 여 API 호출</span><span class="sxs-lookup"><span data-stu-id="749dd-177">API Calls Using DllImport</span></span>  

 <span data-ttu-id="749dd-178">`DllImport`특성은 형식 라이브러리 없이 dll에서 함수를 호출 하는 두 번째 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-178">The `DllImport` attribute provides a second way to call functions in DLLs without type libraries.</span></span> <span data-ttu-id="749dd-179">`DllImport` 는 문을 사용 하는 것과 거의 동일 `Declare` 하지만 함수가 호출 되는 방법을 보다 세밀 하 게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-179">`DllImport` is roughly equivalent to using a `Declare` statement but provides more control over how functions are called.</span></span>  
  
 <span data-ttu-id="749dd-180">`DllImport`호출이 shared ( *static* 이 라고도 함) 메서드를 참조 하는 한 대부분의 Windows API 호출에서을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-180">You can use `DllImport` with most Windows API calls as long as the call refers to a shared (sometimes called *static*) method.</span></span> <span data-ttu-id="749dd-181">클래스의 인스턴스를 필요로 하는 메서드는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-181">You cannot use methods that require an instance of a class.</span></span> <span data-ttu-id="749dd-182">`Declare`문과 달리 `DllImport` 호출은 특성을 사용할 수 없습니다 `MarshalAs` .</span><span class="sxs-lookup"><span data-stu-id="749dd-182">Unlike `Declare` statements, `DllImport` calls cannot use the `MarshalAs` attribute.</span></span>  
  
### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a><span data-ttu-id="749dd-183">DllImport 특성을 사용 하 여 Windows API를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="749dd-183">To call a Windows API using the DllImport attribute</span></span>  
  
1. <span data-ttu-id="749dd-184">**파일** 메뉴에서 **새로 만들기** 를 클릭 한 다음 **프로젝트** 를 클릭 하 여 새 Windows 응용 프로그램 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-184">Open a new Windows Application project by clicking **New** on the **File** menu, and then clicking **Project**.</span></span> <span data-ttu-id="749dd-185">**새 프로젝트** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-185">The **New Project** dialog box appears.</span></span>  
  
2. <span data-ttu-id="749dd-186">Visual Basic 프로젝트 템플릿 목록에서 **Windows 응용 프로그램** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-186">Select **Windows Application** from the list of Visual Basic project templates.</span></span> <span data-ttu-id="749dd-187">새 프로젝트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-187">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="749dd-188">이라는 단추를 `Button2` 시작 폼에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-188">Add a button named `Button2` to the startup form.</span></span>  
  
4. <span data-ttu-id="749dd-189">`Button2`폼의 코드 보기를 두 번 클릭 하 여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-189">Double-click `Button2` to open the code view for the form.</span></span>  
  
5. <span data-ttu-id="749dd-190">에 대 한 액세스를 간소화 하려면 `DllImport` `Imports` 시작 폼 클래스에 대 한 코드의 맨 위에 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-190">To simplify access to `DllImport`, add an `Imports` statement to the top of the code for the startup form class:</span></span>  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
6. <span data-ttu-id="749dd-191">`End Class`폼에 대 한 문 앞에 빈 함수를 선언 하 고 함수 이름을로 `MoveFile` 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-191">Declare an empty function preceding the `End Class` statement for the form, and name the function `MoveFile`.</span></span>  
  
7. <span data-ttu-id="749dd-192">`Public`및 한정자를 `Shared` 함수 선언에 적용 하 고 `MoveFile` Windows API 함수에서 사용 하는 인수에 따라에 대 한 매개 변수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-192">Apply the `Public` and `Shared` modifiers to the function declaration and set parameters for `MoveFile` based on the arguments the Windows API function uses:</span></span>  
  
     [!code-vb[VbVbalrInterop#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#16)]  
  
     <span data-ttu-id="749dd-193">함수에는 유효한 프로시저 이름이 있을 수 있습니다. `DllImport` 특성은 DLL의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-193">Your function can have any valid procedure name; the `DllImport` attribute specifies the name in the DLL.</span></span> <span data-ttu-id="749dd-194">또한 매개 변수 및 반환 값에 대 한 상호 운용성 마샬링을 처리 하므로 API에서 사용 하는 데이터 형식과 비슷한 Visual Studio 데이터 형식을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-194">It also handles interoperability marshaling for the parameters and return values, so you can choose Visual Studio data types that are similar to the data types the API uses.</span></span>  
  
8. <span data-ttu-id="749dd-195">`DllImport`빈 함수에 특성을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-195">Apply the `DllImport` attribute to the empty function.</span></span> <span data-ttu-id="749dd-196">첫 번째 매개 변수는 호출 하는 함수를 포함 하는 DLL의 이름과 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-196">The first parameter is the name and location of the DLL containing the function you are calling.</span></span> <span data-ttu-id="749dd-197">Windows 시스템 디렉터리에 있는 파일에 대 한 경로를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-197">You do not need to specify the path for files located in the Windows system directories.</span></span> <span data-ttu-id="749dd-198">두 번째 매개 변수는 Windows API에서 함수 이름을 지정 하는 명명 된 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-198">The second parameter is a named argument that specifies the name of the function in the Windows API.</span></span> <span data-ttu-id="749dd-199">이 예제에서 특성은에 `DllImport` 대 한 호출이 `MoveFile` KERNEL32.DLL에서로 전달 되도록 `MoveFileW` 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-199">In this example, the `DllImport` attribute forces calls to `MoveFile` to be forwarded to `MoveFileW` in KERNEL32.DLL.</span></span> <span data-ttu-id="749dd-200">메서드는 경로 `MoveFileW` 에서 경로에 파일을 복사 `src` `dst` 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-200">The `MoveFileW` method copies a file from the path `src` to the path `dst`.</span></span>  
  
     [!code-vb[VbVbalrInterop#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#17)]  
  
9. <span data-ttu-id="749dd-201">`Button2_Click`함수를 호출 하는 코드를 이벤트 처리기에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-201">Add code to the `Button2_Click` event handler to call the function:</span></span>  
  
     [!code-vb[VbVbalrInterop#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#18)]  
  
10. <span data-ttu-id="749dd-202">Test.txt 라는 파일을 만들고 하드 드라이브의 C:\Tmp 디렉터리에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-202">Create a file named Test.txt and place it in the C:\Tmp directory on your hard drive.</span></span> <span data-ttu-id="749dd-203">필요한 경우 Tmp 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-203">Create the Tmp directory if necessary.</span></span>  
  
11. <span data-ttu-id="749dd-204">F5 키를 눌러 애플리케이션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-204">Press F5 to start the application.</span></span> <span data-ttu-id="749dd-205">기본 폼이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-205">The main form appears.</span></span>  
  
12. <span data-ttu-id="749dd-206">**Button2** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-206">Click **Button2**.</span></span> <span data-ttu-id="749dd-207">파일을 이동할 수 있는 경우 "파일이 성공적으로 이동 되었습니다." 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="749dd-207">The message "The file was moved successfully" is displayed if the file can be moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="749dd-208">추가 정보</span><span class="sxs-lookup"><span data-stu-id="749dd-208">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="749dd-209">Declare 문</span><span class="sxs-lookup"><span data-stu-id="749dd-209">Declare Statement</span></span>](../../language-reference/statements/declare-statement.md)
- [<span data-ttu-id="749dd-210">자동</span><span class="sxs-lookup"><span data-stu-id="749dd-210">Auto</span></span>](../../language-reference/modifiers/auto.md)
- [<span data-ttu-id="749dd-211">별칭</span><span class="sxs-lookup"><span data-stu-id="749dd-211">Alias</span></span>](../../language-reference/statements/alias-clause.md)
- [<span data-ttu-id="749dd-212">COM Interop</span><span class="sxs-lookup"><span data-stu-id="749dd-212">COM Interop</span></span>](index.md)
- [<span data-ttu-id="749dd-213">관리 코드에서 프로토타입 만들기</span><span class="sxs-lookup"><span data-stu-id="749dd-213">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="749dd-214">콜백 메서드로 대리자 마샬링</span><span class="sxs-lookup"><span data-stu-id="749dd-214">Marshaling a Delegate as a Callback Method</span></span>](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)
