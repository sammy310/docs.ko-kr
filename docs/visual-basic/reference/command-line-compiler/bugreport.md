---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 829c19d2bce40a850d98f4973b1a4e4de31d8ce1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716815"
---
# <a name="-bugreport"></a><span data-ttu-id="b8379-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="b8379-102">-bugreport</span></span>
<span data-ttu-id="b8379-103">버그 보고서를 작성할 때 사용할 수 있는 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8379-104">구문</span><span class="sxs-lookup"><span data-stu-id="b8379-104">Syntax</span></span>  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="b8379-105">인수</span><span class="sxs-lookup"><span data-stu-id="b8379-105">Arguments</span></span>  
  
|<span data-ttu-id="b8379-106">용어</span><span class="sxs-lookup"><span data-stu-id="b8379-106">Term</span></span>|<span data-ttu-id="b8379-107">정의</span><span class="sxs-lookup"><span data-stu-id="b8379-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="b8379-108">필수</span><span class="sxs-lookup"><span data-stu-id="b8379-108">Required.</span></span> <span data-ttu-id="b8379-109">버그 보고서를 포함할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="b8379-110">이름에 공백이 포함 된 경우 파일 이름을 따옴표 ("")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8379-111">주의</span><span class="sxs-lookup"><span data-stu-id="b8379-111">Remarks</span></span>  
 <span data-ttu-id="b8379-112">`file`에 추가 되는 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-112">The following information is added to `file`:</span></span>  
  
- <span data-ttu-id="b8379-113">컴파일할 때 모든 소스 코드 파일의 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-113">A copy of all source-code files in the compilation.</span></span>  
  
- <span data-ttu-id="b8379-114">컴파일에 사용 된 컴파일러 옵션 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-114">A list of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="b8379-115">컴파일러, 공용 언어 런타임 및 운영 체제에 대 한 버전 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
- <span data-ttu-id="b8379-116">컴파일러 출력입니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="b8379-116">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="b8379-117">메시지가 표시 되는 문제에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-117">A description of the problem, for which you are prompted.</span></span>  
  
- <span data-ttu-id="b8379-118">문제를 해결 하는 방법에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="b8379-119">모든 소스 코드 파일의 복사본이 `file`에 포함 되어 있으므로 가능한 가장 짧은 프로그램에서 (의심 스러운) 코드 결함을 재현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b8379-120">`-bugreport` 옵션은 잠재적으로 중요 한 정보를 포함 하는 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="b8379-121">여기에는 현재 시간, 컴파일러 버전, .NET Framework 버전, OS 버전, 사용자 이름, 컴파일러가 실행 된 명령줄 인수, 모든 소스 코드, 참조 된 어셈블리의 이진 형식 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-121">This includes current time, compiler version, .NET Framework version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="b8379-122">ASP.NET 응용 프로그램의 서버 쪽 컴파일에 대해 web.config 파일에서 명령줄 옵션을 지정 하 여이 옵션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an ASP.NET application.</span></span> <span data-ttu-id="b8379-123">이를 방지 하려면 machine.config 파일을 수정 하 여 사용자가 서버에서 컴파일하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="b8379-124">이 옵션을 `-errorreport:prompt`, `-errorreport:queue`또는 `-errorreport:send`와 함께 사용 하 고 응용 프로그램에 내부 컴파일러 오류가 발생 하는 경우 `file`의 정보가 Microsoft Corporation으로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="b8379-125">이 정보는 Microsoft 엔지니어가 오류의 원인을 파악 하는 데 도움이 되며 Visual Basic의 다음 릴리스를 개선 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="b8379-126">기본적으로 Microsoft로 전송 되는 정보는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="b8379-127">그러나 기본적으로 사용 하도록 설정 된 `-errorreport:queue`를 사용 하 여 응용 프로그램을 컴파일하면 응용 프로그램에서 해당 오류 보고서를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="b8379-128">그러면 컴퓨터의 관리자가 로그인 할 때 오류 보고 시스템에 로그온 한 이후에 발생 한 오류 보고서를 Microsoft에 전달할 수 있는 팝업 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8379-129">`-bugreport` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-129">The `-bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8379-130">예</span><span class="sxs-lookup"><span data-stu-id="b8379-130">Example</span></span>  
 <span data-ttu-id="b8379-131">다음 예제에서는 `T2.vb` 컴파일하고 모든 버그 보고 정보를 파일 `Problem.txt`에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b8379-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```console  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8379-132">참조</span><span class="sxs-lookup"><span data-stu-id="b8379-132">See also</span></span>

- [<span data-ttu-id="b8379-133">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="b8379-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="b8379-134">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8379-134">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="b8379-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="b8379-135">-errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [<span data-ttu-id="b8379-136">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="b8379-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="b8379-137">[Ws-securitypolicy에 대 한 trustLevel 요소 (ASP.NET Settings 스키마)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b8379-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
