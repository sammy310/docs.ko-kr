---
title: '@(지시 파일 지정)(Visual Basic)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: 6b993a6399eec4e203821109db153aadf246cbac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838120"
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="54397-102">@(지시 파일 지정)(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54397-102">@ (Specify Response File) (Visual Basic)</span></span>
<span data-ttu-id="54397-103">컴파일러 옵션을 포함 하는 파일 및 컴파일할 소스 코드 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54397-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54397-104">구문</span><span class="sxs-lookup"><span data-stu-id="54397-104">Syntax</span></span>  
  
```  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="54397-105">인수</span><span class="sxs-lookup"><span data-stu-id="54397-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="54397-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="54397-106">Required.</span></span> <span data-ttu-id="54397-107">컴파일러 옵션이 나 컴파일할 소스 코드 파일을 나열 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="54397-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="54397-108">파일 이름을 따옴표로 묶습니다 ("")에 공백이 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="54397-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54397-109">설명</span><span class="sxs-lookup"><span data-stu-id="54397-109">Remarks</span></span>  
 <span data-ttu-id="54397-110">컴파일러는 컴파일러 옵션 및 명령줄에서 지정 된 것 처럼 응답 파일에 지정 된 소스 코드 파일을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="54397-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="54397-111">컴파일에서 둘 이상의 응답 파일을 지정 하려면 다음과 같은 여러 지시 파일 옵션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54397-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>  
  
```  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="54397-112">응답에서 파일, 여러 컴파일러 옵션 및 소스 코드 파일은 한 줄에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54397-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="54397-113">단일 컴파일러 옵션 사양 (여러 줄에 걸쳐 없습니다) 하는 한 줄에 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54397-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="54397-114">응답 파일에는 시작 하는 주석을 포함할 수 있습니다는 `#` 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="54397-114">Response files can have comments that begin with the `#` symbol.</span></span>  
  
 <span data-ttu-id="54397-115">하나 이상의 응답 파일에 지정 된 옵션을 사용 하 여 명령줄에 지정 된 옵션을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54397-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="54397-116">컴파일러는으로 명령 옵션을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="54397-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="54397-117">따라서 명령줄 인수는 지시 파일에서 앞에 나열 된 옵션을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54397-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="54397-118">반대로, 응답 파일에에서 있는 옵션 명령줄 또는 다른 지시 파일에서 이전에 나열 된 옵션을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="54397-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="54397-119">Visual Basic Vbc.exe 파일과 동일한 디렉터리에 위치한 Vbc.rsp 파일을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="54397-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="54397-120">Vbc.rsp 파일을 하지 않는 한 기본적으로 포함 됩니다는 `-noconfig` 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="54397-120">The Vbc.rsp file is included by default unless the `-noconfig` option is used.</span></span> <span data-ttu-id="54397-121">자세한 내용은 [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="54397-121">For more information, see [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54397-122">`@` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="54397-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54397-123">예제</span><span class="sxs-lookup"><span data-stu-id="54397-123">Example</span></span>  
 <span data-ttu-id="54397-124">샘플 응답 파일에서 다음 줄은입니다.</span><span class="sxs-lookup"><span data-stu-id="54397-124">The following lines are from a sample response file.</span></span>  
  
```console
# build the first output file  
-target:exe   
-out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="54397-125">예제</span><span class="sxs-lookup"><span data-stu-id="54397-125">Example</span></span>  
 <span data-ttu-id="54397-126">다음 예제에서는 사용 하는 방법에 설명 합니다 `@` 라는 지시 파일이 사용 하 여 옵션 `File1.rsp`합니다.</span><span class="sxs-lookup"><span data-stu-id="54397-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>  
  
```console
vbc @file1.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="54397-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="54397-127">See also</span></span>

- [<span data-ttu-id="54397-128">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="54397-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="54397-129">-noconfig</span><span class="sxs-lookup"><span data-stu-id="54397-129">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="54397-130">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="54397-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
