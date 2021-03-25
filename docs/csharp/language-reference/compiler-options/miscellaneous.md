---
description: 기타 C# 컴파일러 옵션입니다. 이러한 옵션은 컴파일러에 일반 옵션을 제공합니다.
title: 다른 범주에 맞지 않는 C# 컴파일러 옵션
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- ResponseFiles compiler option [C#]
- NoLogo compiler option [C#]
- NoConfig compiler option [C#]
ms.openlocfilehash: ec7d9c3685c9acb5ca3cda28aca55abb26b836cf
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482445"
---
# <a name="miscellaneous-c-compiler-options"></a><span data-ttu-id="9e382-104">기타 C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="9e382-104">Miscellaneous C# Compiler Options</span></span>

<span data-ttu-id="9e382-105">다음 옵션은 기타 컴파일러 동작을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-105">The following options control miscellaneous compiler behavior.</span></span> <span data-ttu-id="9e382-106">새 MSBuild 구문은 **굵게** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-106">The new MSBuild syntax is shown in **Bold**.</span></span> <span data-ttu-id="9e382-107">이전 *csc.exe* 구문은 `code style`에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-107">The older *csc.exe* syntax is shown in `code style`.</span></span>

- <span data-ttu-id="9e382-108">**ResponseFiles** / `-@`: 추가 옵션에 대한 지시 파일을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-108">**ResponseFiles** / `-@`: Read response file for more options.</span></span>
- <span data-ttu-id="9e382-109">**NoLogo** / `-nologo`: 컴파일러 저작권 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-109">**NoLogo** / `-nologo` : Suppress compiler copyright message.</span></span>
- <span data-ttu-id="9e382-110">**NoConfig** / `-noconfig`: *CSC.RSP* 파일을 자동으로 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-110">**NoConfig** / `-noconfig`: Don't auto include *CSC.RSP* file.</span></span>

## <a name="responsefiles"></a><span data-ttu-id="9e382-111">ResponseFiles</span><span class="sxs-lookup"><span data-stu-id="9e382-111">ResponseFiles</span></span>

<span data-ttu-id="9e382-112">**ResponseFiles** 옵션을 사용하면 컴파일 옵션과 컴파일할 소스 코드 파일이 포함된 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-112">The **ResponseFiles** option lets you specify a file that contains compiler options and source code files to compile.</span></span>

```xml
<ResponseFiles>response_file</ResponseFiles>
```

<span data-ttu-id="9e382-113">`response_file`은 컴파일러 옵션이나 컴파일할 소스 코드 파일이 나열하는 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-113">The `response_file` specifies the file that lists compiler options or source code files to compile.</span></span> <span data-ttu-id="9e382-114">컴파일러 옵션 및 소스 코드 파일은 명령줄에 지정된 것처럼 컴파일러에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-114">The compiler options and source code files will be processed by the compiler as if they had been specified on the command line.</span></span> <span data-ttu-id="9e382-115">컴파일에 지시 파일을 둘 이상 지정하려면 여러 지시 파일 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-115">To specify more than one response file in a compilation, specify multiple response file options.</span></span> <span data-ttu-id="9e382-116">지시 파일에서 여러 컴파일러 옵션과 소스 코드 파일이 한 줄에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-116">In a response file, multiple compiler options and source code files can appear on one line.</span></span> <span data-ttu-id="9e382-117">단일 컴파일러 옵션 사양은 한 줄에 표시되어야 합니다(여러 줄에 걸쳐 있을 수 없음).</span><span class="sxs-lookup"><span data-stu-id="9e382-117">A single compiler option specification must appear on one line (can't span multiple lines).</span></span> <span data-ttu-id="9e382-118">지시 파일은 # 기호로 시작하는 주석을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-118">Response files can have comments that begin with the # symbol.</span></span> <span data-ttu-id="9e382-119">지시 파일 내에서 컴파일러 옵션을 지정하는 것은 명령줄에서 해당 명령을 실행하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-119">Specifying compiler options from within a response file is just like issuing those commands on the command line.</span></span> <span data-ttu-id="9e382-120">컴파일러는 읽은대로 명령 옵션을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-120">The compiler processes the command options as they're read.</span></span> <span data-ttu-id="9e382-121">명령줄 인수는 지시 파일에서 이전에 나열된 옵션을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-121">Command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="9e382-122">반대로 지시 파일의 옵션은 명령줄 또는 다른 지시 파일에서 이전에 나열된 옵션을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-122">Conversely, options in a response file will override options listed previously on the command line or in other response files.</span></span> <span data-ttu-id="9e382-123">C#에서는 csc.exe 파일과 동일한 디렉터리에 있는 csc.rsp 파일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-123">C# provides the csc.rsp file, which is located in the same directory as the csc.exe file.</span></span> <span data-ttu-id="9e382-124">지시 파일 형식에 대한 자세한 내용은 [**NoConfig**](#noconfig)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e382-124">For more information about the response file format, see [**NoConfig**](#noconfig).</span></span> <span data-ttu-id="9e382-125">Visual Studio 개발 환경에서는 이 컴파일러 옵션을 설정할 수 없으며 프로그래밍 방식으로 변경할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-125">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span> <span data-ttu-id="9e382-126">다음은 샘플 지시 파일의 몇 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-126">The following are a few lines from a sample response file:</span></span>

```console
# build the first output file
-target:exe -out:MyExe.exe source1.cs source2.cs
```

## <a name="nologo"></a><span data-ttu-id="9e382-127">NoLogo</span><span class="sxs-lookup"><span data-stu-id="9e382-127">NoLogo</span></span>

<span data-ttu-id="9e382-128">**NoLogo** 옵션은 컴파일러가 시작될 때 로그온 배너의 표시를 억제하고 컴파일하는 동안 정보 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-128">The **NoLogo** option suppresses display of the sign-on banner when the compiler starts up and display of informational messages during compiling.</span></span>

```xml
<NoLogo>true</NoLogo>
```

## <a name="noconfig"></a><span data-ttu-id="9e382-129">NoConfig</span><span class="sxs-lookup"><span data-stu-id="9e382-129">NoConfig</span></span>

<span data-ttu-id="9e382-130">**NoConfig** 옵션은 *csc.rsp* 파일을 사용하여 컴파일하지 않도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-130">The **NoConfig** option tells the compiler not to compile with the *csc.rsp* file.</span></span>

```xml
<NoConfig>true</NoConfig>
```

<span data-ttu-id="9e382-131">*csc.rsp* 파일은 .NET Framework와 함께 제공되는 모든 어셈블리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-131">The *csc.rsp* file references all the assemblies shipped with .NET Framework.</span></span> <span data-ttu-id="9e382-132">Visual Studio .NET 개발 환경에 포함된 실제 참조는 프로젝트 형식에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-132">The actual references that the Visual Studio .NET development environment includes depend on the project type.</span></span> <span data-ttu-id="9e382-133">*csc.rsp* 파일을 수정하고 모든 컴파일에 포함되어야 하는 추가 컴파일러 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-133">You can modify the *csc.rsp* file and specify additional compiler options that should be included in every compilation.</span></span> <span data-ttu-id="9e382-134">컴파일러가 *csc.rsp* 파일의 설정을 찾아서 사용하지 않도록 하려면 **NoConfig** 를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-134">If you don't want the compiler to look for and use the settings in the *csc.rsp* file, specify **NoConfig**.</span></span> <span data-ttu-id="9e382-135">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e382-135">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>
