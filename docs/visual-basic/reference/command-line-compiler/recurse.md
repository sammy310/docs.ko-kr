---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 7ded2b7d102430d8d4e545da5ab6ce8bafe3609e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095424"
---
# <a name="-recurse"></a><span data-ttu-id="a559f-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="a559f-102">-recurse</span></span>

<span data-ttu-id="a559f-103">지정된 디렉터리 또는 프로젝트 디렉터리의 모든 자식 디렉터리에 있는 소스 코드 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="a559f-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a559f-104">구문</span><span class="sxs-lookup"><span data-stu-id="a559f-104">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="a559f-105">인수</span><span class="sxs-lookup"><span data-stu-id="a559f-105">Arguments</span></span>  

 `dir`  
 <span data-ttu-id="a559f-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a559f-106">Optional.</span></span> <span data-ttu-id="a559f-107">검색을 시작하려는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="a559f-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="a559f-108">지정하지 않으면 프로젝트 디렉터리에서 검색이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="a559f-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="a559f-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a559f-109">Required.</span></span> <span data-ttu-id="a559f-110">검색할 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a559f-110">The file(s) to search for.</span></span> <span data-ttu-id="a559f-111">와일드카드 문자가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a559f-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a559f-112">설명</span><span class="sxs-lookup"><span data-stu-id="a559f-112">Remarks</span></span>  

 <span data-ttu-id="a559f-113">파일 이름에 와일드카드를 사용하면 `-recurse`를 사용하지 않고 프로젝트 디렉터리에서 일치하는 모든 파일을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a559f-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="a559f-114">출력 파일 이름이 지정되지 않은 경우 컴파일러는 처리된 첫 번째 입력 파일의 출력 파일 이름을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a559f-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="a559f-115">이는 일반적으로 사전순으로 볼 때 컴파일되는 파일 목록의 첫 번째 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a559f-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="a559f-116">따라서 `-out` 옵션을 사용하여 출력 파일을 지정하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a559f-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a559f-117">Visual Studio 개발 환경 내에서는 `-recurse` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a559f-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a559f-118">예제</span><span class="sxs-lookup"><span data-stu-id="a559f-118">Example</span></span>  

 <span data-ttu-id="a559f-119">다음 명령은 현재 디렉터리에 있는 모든 Visual Basic 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="a559f-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="a559f-120">다음 명령은 `Test\ABC` 디렉터리와 그 아래 디렉터리에 있는 모든 Visual Basic 파일을 컴파일한 다음, `Test.ABC.dll`을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a559f-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a559f-121">참조</span><span class="sxs-lookup"><span data-stu-id="a559f-121">See also</span></span>

- [<span data-ttu-id="a559f-122">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="a559f-122">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="a559f-123">-out(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a559f-123">-out (Visual Basic)</span></span>](out.md)
- [<span data-ttu-id="a559f-124">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="a559f-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
