---
title: -platform
ms.date: 03/13/2018
helpviewer_keywords:
- platform compiler option [Visual Basic]
- /platform compiler option [Visual Basic]
- -platform compiler option [Visual Basic]
ms.assetid: f9bc61e6-e854-4ae1-87b9-d6244de23fd1
ms.openlocfilehash: a6226b73d5d5d4d48a71afe39e8a546019d4c0bc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352350"
---
# <a name="-platform-visual-basic"></a><span data-ttu-id="67449-102">-platform (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67449-102">-platform (Visual Basic)</span></span>
<span data-ttu-id="67449-103">출력 파일을 실행할 수 있는 CLR(공용 언어 런타임) 플랫폼 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67449-103">Specifies which platform version of common language runtime (CLR) can run the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67449-104">구문</span><span class="sxs-lookup"><span data-stu-id="67449-104">Syntax</span></span>  
  
```console  
-platform:{ x86 | x64 | Itanium | arm | anycpu | anycpu32bitpreferred }  
```  
  
## <a name="arguments"></a><span data-ttu-id="67449-105">인수</span><span class="sxs-lookup"><span data-stu-id="67449-105">Arguments</span></span>  
  
|<span data-ttu-id="67449-106">용어</span><span class="sxs-lookup"><span data-stu-id="67449-106">Term</span></span>|<span data-ttu-id="67449-107">정의</span><span class="sxs-lookup"><span data-stu-id="67449-107">Definition</span></span>|  
|---|---|  
|`x86`|<span data-ttu-id="67449-108">32비트, x86 호환 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="67449-108">Compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>|  
|`x64`|<span data-ttu-id="67449-109">AMD64 또는 EM64T 명령 집합을 지원하는 컴퓨터에서 64비트 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="67449-109">Compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>|  
|`Itanium`|<span data-ttu-id="67449-110">Itanium 프로세서 탑재 컴퓨터에서 64비트 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="67449-110">Compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>|  
|`arm`|<span data-ttu-id="67449-111">ARM(고급 RISC 컴퓨터) 프로세서를 탑재한 컴퓨터에서 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="67449-111">Compiles your assembly to be run on a computer with an ARM (Advanced RISC Machine) processor.</span></span>|  
|`anycpu`|<span data-ttu-id="67449-112">임의의 플랫폼에서 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="67449-112">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="67449-113">애플리케이션은 32비트 버전 Windows에서는 32비트 애플리케이션으로, 64비트 버전 Windows에서는 64비트 애플리케이션으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="67449-113">The application will run as a 32-bit application on 32-bit versions of Windows and as a 64-bit application on 64-bit versions of Windows.</span></span> <span data-ttu-id="67449-114">이 플래그가 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="67449-114">This flag is the default value.</span></span>|  
|`anycpu32bitpreferred`|<span data-ttu-id="67449-115">임의의 플랫폼에서 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="67449-115">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="67449-116">애플리케이션은 32비트 및 64비트 버전 Windows 둘 다에서 32비트 애플리케이션으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="67449-116">The application will run as a 32-bit application on both 32-bit and 64-bit versions of Windows.</span></span> <span data-ttu-id="67449-117">이 플래그는 실행 파일 ()에 대해서만 유효 합니다. EXE)를 사용 하려면 .NET Framework 4.5가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="67449-117">This flag is valid only for executables (.EXE) and requires .NET Framework 4.5.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67449-118">주의</span><span class="sxs-lookup"><span data-stu-id="67449-118">Remarks</span></span>  
 <span data-ttu-id="67449-119">출력 파일의 대상 프로세서 유형을 지정하려면 `-platform` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="67449-119">Use the `-platform` option to specify the type of processor targeted by the output file.</span></span>  
  
 <span data-ttu-id="67449-120">일반적으로 Visual Basic에서 작성된 .NET Framework 어셈블리는 플랫폼에 관계없이 동일하게 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="67449-120">In general, .NET Framework assemblies written in Visual Basic will run the same regardless of the platform.</span></span> <span data-ttu-id="67449-121">그러나 플랫폼별로 동작이 다른 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67449-121">However, there are some cases that behave differently on different platforms.</span></span> <span data-ttu-id="67449-122">이러한 경우의 일반적인 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="67449-122">These common cases are:</span></span>  
  
- <span data-ttu-id="67449-123">포인터 형식과 같이 플랫폼에 따라 크기가 달라지는 멤버를 포함하는 구조체</span><span class="sxs-lookup"><span data-stu-id="67449-123">Structures that contain members that change size depending on the platform, such as any pointer type.</span></span>  
  
- <span data-ttu-id="67449-124">상수 크기를 포함하는 포인터 산술 연산</span><span class="sxs-lookup"><span data-stu-id="67449-124">Pointer arithmetic that includes constant sizes.</span></span>  
  
- <span data-ttu-id="67449-125">핸들에 대해 `Integer` 대신 <xref:System.IntPtr>를 사용하는 잘못된 플랫폼 호출 또는 COM 선언</span><span class="sxs-lookup"><span data-stu-id="67449-125">Incorrect platform invoke or COM declarations that use `Integer` for handles instead of <xref:System.IntPtr>.</span></span>  
  
- <span data-ttu-id="67449-126"><xref:System.IntPtr>을 `Integer`로 캐스팅</span><span class="sxs-lookup"><span data-stu-id="67449-126">Casting <xref:System.IntPtr> to `Integer`.</span></span>  
  
- <span data-ttu-id="67449-127">일부 플랫폼에만 있는 구성 요소를 통한 플랫폼 호출 또는 COM interop 사용</span><span class="sxs-lookup"><span data-stu-id="67449-127">Using platform invoke or COM interop with components that do not exist on all platforms.</span></span>  
  
 <span data-ttu-id="67449-128">**-Platform** 옵션은 코드가 실행 되는 아키텍처에 대 한 가정을 알고 있는 경우 몇 가지 문제를 완화 합니다.</span><span class="sxs-lookup"><span data-stu-id="67449-128">The **-platform** option will mitigate some issues if you know you have made assumptions about the architecture your code will run on.</span></span> <span data-ttu-id="67449-129">구체적으로는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="67449-129">Specifically:</span></span>  
  
- <span data-ttu-id="67449-130">애플리케이션이 32비트 컴퓨터에서 실행되는데 64비트 플랫폼을 대상으로 지정하는 경우에는 오류 메시지가 훨씬 더 일찍 표시되며, 이 스위치를 사용하지 않아 발생하는 오류보다는 문제 자체에 대한 내용이 중점적으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67449-130">If you decide to target a 64-bit platform, and the application is run on a 32-bit machine, the error message comes much earlier and is more targeted at the problem than the error that occurs without using this switch.</span></span>  
  
- <span data-ttu-id="67449-131">옵션에 대해 `x86` 플래그를 설정한 후 애플리케이션을 64비트 컴퓨터에서 실행하면 애플리케이션이 기본적으로 실행되지 않고 WOW 하위 시스템에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="67449-131">If you set the `x86` flag on the option and the application is subsequently run on a 64-bit machine, the application will run in the WOW subsystem instead of running natively.</span></span>  
  
 <span data-ttu-id="67449-132">64비트 Windows 운영 체제:</span><span class="sxs-lookup"><span data-stu-id="67449-132">On a 64-bit Windows operating system:</span></span>  
  
- <span data-ttu-id="67449-133">`-platform:x86`으로 컴파일된 어셈블리는 WOW64에서 실행되는 32비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="67449-133">Assemblies compiled with `-platform:x86` will execute on the 32-bit CLR running under WOW64.</span></span>  
  
- <span data-ttu-id="67449-134">`-platform:anycpu`로 컴파일된 실행 파일은 64비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="67449-134">Executables compiled with the `-platform:anycpu` will execute on the 64-bit CLR.</span></span>  
  
- <span data-ttu-id="67449-135">`-platform:anycpu`로 컴파일된 DLL은 이 DLL이 로드된 프로세스와 동일한 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="67449-135">A DLL compiled with the `-platform:anycpu` will execute on the same CLR as the process into which it loaded.</span></span>  
  
- <span data-ttu-id="67449-136">`-platform:anycpu32bitpreferred`로 컴파일된 실행 파일은 32비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="67449-136">Executables that are compiled with `-platform:anycpu32bitpreferred` will execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="67449-137">64 비트 버전의 Windows에서 실행할 응용 프로그램을 개발 하는 방법에 대 한 자세한 내용은 [64 비트 응용 프로그램](../../../framework/64-bit-apps.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="67449-137">For more information about how to develop an application to run on a 64-bit version of Windows, see [64-bit Applications](../../../framework/64-bit-apps.md).</span></span>  
  
### <a name="to-set--platform-in-the-visual-studio-ide"></a><span data-ttu-id="67449-138">Visual Studio IDE에서 플랫폼을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="67449-138">To set -platform in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="67449-139">**솔루션 탐색기**에서 프로젝트를 선택 하 고 **프로젝트** 메뉴를 연 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="67449-139">In **Solution Explorer**, choose the project, open the **Project** menu, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="67449-140">**컴파일** 탭에서 **32 비트 선호** 확인란을 선택 하거나 선택 취소 하거나 **대상 CPU** 목록에서 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67449-140">On the **Compile** tab, select or clear the **Prefer 32-bit** check box, or, in the **Target CPU** list, choose a value.</span></span>  
  
     <span data-ttu-id="67449-141">자세한 내용은 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67449-141">For more information, see [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="example"></a><span data-ttu-id="67449-142">예제</span><span class="sxs-lookup"><span data-stu-id="67449-142">Example</span></span>  
 <span data-ttu-id="67449-143">다음 예제에서는 `-platform` 컴파일러 옵션을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="67449-143">The following example illustrates how to use the `-platform` compiler option.</span></span>  
  
```console
vbc -platform:x86 myFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="67449-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67449-144">See also</span></span>

- [<span data-ttu-id="67449-145">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67449-145">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="67449-146">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="67449-146">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="67449-147">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="67449-147">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
