---
description: '@(C# 컴파일러 옵션)'
title: '@(C# 컴파일러 옵션)'
ms.date: 07/20/2015
f1_keywords:
- '@'
helpviewer_keywords:
- response files, specifying for compilation [C#]
- '@ compiler option'
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
ms.openlocfilehash: 89a057cba6e0d23c15fc9b652e5bfbc89b6ecbaa
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128649"
---
# <a name="-c-compiler-options"></a><span data-ttu-id="e225f-103">@(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="e225f-103">@ (C# Compiler Options)</span></span>
<span data-ttu-id="e225f-104">@ 옵션을 사용하면 컴파일러 옵션과 컴파일할 소스 코드 파일이 포함된 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e225f-104">The @ option lets you specify a file that contains compiler options and source code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e225f-105">구문</span><span class="sxs-lookup"><span data-stu-id="e225f-105">Syntax</span></span>  
  
```console  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="e225f-106">인수</span><span class="sxs-lookup"><span data-stu-id="e225f-106">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="e225f-107">컴파일러 옵션이나 컴파일할 소스 코드 파일이 나열된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e225f-107">A file that lists compiler options or source code files to compile.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e225f-108">설명</span><span class="sxs-lookup"><span data-stu-id="e225f-108">Remarks</span></span>  
 <span data-ttu-id="e225f-109">컴파일러 옵션 및 소스 코드 파일은 명령줄에 지정된 것처럼 컴파일러에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="e225f-109">The compiler options and source code files will be processed by the compiler just as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="e225f-110">컴파일에 지시 파일을 둘 이상 지정하려면 여러 지시 파일 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e225f-110">To specify more than one response file in a compilation, specify multiple response file options.</span></span> <span data-ttu-id="e225f-111">예:</span><span class="sxs-lookup"><span data-stu-id="e225f-111">For example:</span></span>  
  
```console  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="e225f-112">지시 파일에서 여러 컴파일러 옵션과 소스 코드 파일이 한 줄에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e225f-112">In a response file, multiple compiler options and source code files can appear on one line.</span></span> <span data-ttu-id="e225f-113">단일 컴파일러 옵션 사양은 한 줄에 표시되어야 합니다(여러 줄에 걸쳐 있을 수 없음).</span><span class="sxs-lookup"><span data-stu-id="e225f-113">A single compiler option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="e225f-114">지시 파일은 # 기호로 시작하는 주석을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e225f-114">Response files can have comments that begin with the # symbol.</span></span>  
  
 <span data-ttu-id="e225f-115">지시 파일 내에서 컴파일러 옵션을 지정하는 것은 명령줄에서 해당 명령을 실행하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e225f-115">Specifying compiler options from within a response file is just like issuing those commands on the command line.</span></span> <span data-ttu-id="e225f-116">자세한 내용은 [명령줄에서 빌드](./how-to-set-environment-variables-for-the-visual-studio-command-line.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e225f-116">See [Building from the Command Line](./how-to-set-environment-variables-for-the-visual-studio-command-line.md) for more information.</span></span>  
  
 <span data-ttu-id="e225f-117">명령 옵션이 발견되면 컴파일러에서 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="e225f-117">The compiler processes the command options as they are encountered.</span></span> <span data-ttu-id="e225f-118">따라서, 명령줄 인수는 지시 파일에서 이전에 나열된 옵션을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e225f-118">Therefore, command line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="e225f-119">반대로 지시 파일의 옵션은 명령줄 또는 다른 지시 파일에서 이전에 나열된 옵션을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e225f-119">Conversely, options in a response file will override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="e225f-120">C#에서는 csc.exe 파일과 동일한 디렉터리에 있는 csc.rsp 파일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e225f-120">C# provides the csc.rsp file, which is located in the same directory as the csc.exe file.</span></span> <span data-ttu-id="e225f-121">csc.rsp에 대한 자세한 내용은 [-noconfig](./noconfig-compiler-option.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e225f-121">See [-noconfig](./noconfig-compiler-option.md) for more information on csc.rsp.</span></span>  
  
 <span data-ttu-id="e225f-122">Visual Studio 개발 환경에서는 이 컴파일러 옵션을 설정할 수 없으며 프로그래밍 방식으로 변경할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e225f-122">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e225f-123">예제</span><span class="sxs-lookup"><span data-stu-id="e225f-123">Example</span></span>  
 <span data-ttu-id="e225f-124">다음은 샘플 지시 파일의 몇 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="e225f-124">The following are a few lines from a sample response file:</span></span>  
  
```console  
# build the first output file  
-target:exe -out:MyExe.exe source1.cs source2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="e225f-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e225f-125">See also</span></span>

- [<span data-ttu-id="e225f-126">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="e225f-126">C# Compiler Options</span></span>](./index.md)
