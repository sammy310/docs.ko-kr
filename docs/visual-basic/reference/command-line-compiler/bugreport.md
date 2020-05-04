---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 02d84bceb0242988c70889ddd5d3dc7530f6e808
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793543"
---
# <a name="-bugreport"></a><span data-ttu-id="a2acf-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="a2acf-102">-bugreport</span></span>

<span data-ttu-id="a2acf-103">버그 보고서를 작성할 때 사용할 수 있는 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-103">Creates a file that you can use when you file a bug report.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2acf-104">구문</span><span class="sxs-lookup"><span data-stu-id="a2acf-104">Syntax</span></span>

```console
-bugreport:file
```

## <a name="arguments"></a><span data-ttu-id="a2acf-105">인수</span><span class="sxs-lookup"><span data-stu-id="a2acf-105">Arguments</span></span>

|<span data-ttu-id="a2acf-106">용어</span><span class="sxs-lookup"><span data-stu-id="a2acf-106">Term</span></span>|<span data-ttu-id="a2acf-107">정의</span><span class="sxs-lookup"><span data-stu-id="a2acf-107">Definition</span></span>|
|---|---|
|`file`|<span data-ttu-id="a2acf-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a2acf-108">Required.</span></span> <span data-ttu-id="a2acf-109">버그 보고서를 포함할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="a2acf-110">파일 이름에 공백이 있으면 이름을 따옴표(" ")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a2acf-111">설명</span><span class="sxs-lookup"><span data-stu-id="a2acf-111">Remarks</span></span>

<span data-ttu-id="a2acf-112">`file`에 추가되는 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-112">The following information is added to `file`:</span></span>

- <span data-ttu-id="a2acf-113">컴파일에 포함된 모든 소스 코드 파일의 복사본.</span><span class="sxs-lookup"><span data-stu-id="a2acf-113">A copy of all source-code files in the compilation.</span></span>

- <span data-ttu-id="a2acf-114">컴파일에 사용된 컴파일러 옵션의 목록.</span><span class="sxs-lookup"><span data-stu-id="a2acf-114">A list of the compiler options used in the compilation.</span></span>

- <span data-ttu-id="a2acf-115">컴파일러, 공용 언어 런타임 및 운영 체제에 대한 버전 정보.</span><span class="sxs-lookup"><span data-stu-id="a2acf-115">Version information about your compiler, common language runtime, and operating system.</span></span>

- <span data-ttu-id="a2acf-116">컴파일러 출력입니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="a2acf-116">Compiler output, if any.</span></span>

- <span data-ttu-id="a2acf-117">메시지가 표시된 문제에 대한 설명.</span><span class="sxs-lookup"><span data-stu-id="a2acf-117">A description of the problem, for which you are prompted.</span></span>

- <span data-ttu-id="a2acf-118">오류 메시지가 표시된 문제 해결 방법에 대한 설명.</span><span class="sxs-lookup"><span data-stu-id="a2acf-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>

<span data-ttu-id="a2acf-119">모든 소스 코드 파일의 복사본이 `file`에 포함되기 때문에 최대한 짧은 프로그램으로 의심스러운 코드 결함을 재현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2acf-120">`-bugreport` 옵션은 잠재적으로 중요한 정보를 포함하는 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="a2acf-121">여기에는 현재 시간, 컴파일러 버전, .NET Framework 버전, OS 버전, 사용자 이름, 컴파일러를 실행한 명령줄 인수, 모든 소스 코드, 참조된 어셈블리의 이진 형식 등이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-121">This includes current time, compiler version, .NET Framework version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="a2acf-122">ASP.NET 애플리케이션의 서버 쪽 컴파일에 대한 Web.config 파일에서 명령줄 옵션을 지정하여 이 옵션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an ASP.NET application.</span></span> <span data-ttu-id="a2acf-123">이를 방지하려면 사용자가 서버에서 컴파일하지 못하도록 Machine.config 파일을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>

<span data-ttu-id="a2acf-124">이 옵션을 `-errorreport:prompt`, `-errorreport:queue` 또는 `-errorreport:send`와 함께 사용할 때 애플리케이션에서 내부 컴파일러 오류가 발생하는 경우 `file`의 정보가 Microsoft로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="a2acf-125">이 정보는 Microsoft 엔지니어가 오류의 원인을 파악하는 데 도움이 되며 Visual Basic의 다음 릴리스를 개선하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="a2acf-126">기본적으로 어떠한 정보도 Microsoft로 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="a2acf-127">그러나 기본적으로 사용하도록 설정되는 `-errorreport:queue`를 사용하여 애플리케이션을 컴파일하면 애플리케이션이 해당 오류 보고서를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="a2acf-128">그러면 컴퓨터의 관리자가 로그인할 때 오류 보고 시스템에 관리자가 로그온 이후 발생한 모든 오류 보고서를 Microsoft에 전달할 수 있는 팝업 창이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>

> [!NOTE]
> <span data-ttu-id="a2acf-129">Visual Studio 개발 환경에서는 `-bugreport` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-129">The `-bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="a2acf-130">예제</span><span class="sxs-lookup"><span data-stu-id="a2acf-130">Example</span></span>

<span data-ttu-id="a2acf-131">다음 예제에서는 *T2.vb*를 컴파일하고 *Problem.txt* 파일에 모든 버그 보고 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-131">The following example compiles *T2.vb* and puts all bug-reporting information in the file *Problem.txt*.</span></span>

```console
vbc -bugreport:problem.txt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="a2acf-132">참조</span><span class="sxs-lookup"><span data-stu-id="a2acf-132">See also</span></span>

- [<span data-ttu-id="a2acf-133">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="a2acf-133">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="a2acf-134">-debug(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2acf-134">-debug (Visual Basic)</span></span>](debug.md)
- [<span data-ttu-id="a2acf-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="a2acf-135">-errorreport</span></span>](errorreport.md)
- [<span data-ttu-id="a2acf-136">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="a2acf-136">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- <span data-ttu-id="a2acf-137">[trustLevel Element for securityPolicy(ASP.NET 설정 스키마)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a2acf-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
