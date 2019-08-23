---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 4281c7bf5a7972d323e1e649aaef437c7ee901ff
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956274"
---
# <a name="-recurse"></a><span data-ttu-id="4b206-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="4b206-102">-recurse</span></span>
<span data-ttu-id="4b206-103">지정 된 디렉터리 또는 프로젝트 디렉터리의 모든 자식 디렉터리에 있는 소스 코드 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="4b206-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b206-104">구문</span><span class="sxs-lookup"><span data-stu-id="4b206-104">Syntax</span></span>  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="4b206-105">인수</span><span class="sxs-lookup"><span data-stu-id="4b206-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="4b206-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4b206-106">Optional.</span></span> <span data-ttu-id="4b206-107">검색을 시작하려는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="4b206-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="4b206-108">지정 하지 않으면 프로젝트 디렉터리에서 검색이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b206-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="4b206-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="4b206-109">Required.</span></span> <span data-ttu-id="4b206-110">검색할 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4b206-110">The file(s) to search for.</span></span> <span data-ttu-id="4b206-111">와일드카드 문자가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b206-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b206-112">설명</span><span class="sxs-lookup"><span data-stu-id="4b206-112">Remarks</span></span>  
 <span data-ttu-id="4b206-113">를 사용 `-recurse`하지 않고 파일 이름에 와일드 카드를 사용 하 여 프로젝트 디렉터리에서 일치 하는 모든 파일을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b206-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="4b206-114">출력 파일 이름이 지정 되지 않은 경우 컴파일러는 처리 된 첫 번째 입력 파일의 출력 파일 이름을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b206-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="4b206-115">이 파일은 일반적으로 사전순으로 볼 때 컴파일되는 파일 목록의 첫 번째 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4b206-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="4b206-116">따라서 `-out` 옵션을 사용 하 여 출력 파일을 지정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4b206-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b206-117">이 `-recurse` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b206-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b206-118">예제</span><span class="sxs-lookup"><span data-stu-id="4b206-118">Example</span></span>  
 <span data-ttu-id="4b206-119">다음 명령은 현재 디렉터리에 있는 모든 Visual Basic 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="4b206-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="4b206-120">다음 명령은 `Test\ABC` 디렉터리의 모든 Visual Basic 파일 및 그 아래에 있는 모든 디렉터리를 컴파일한 다음를 생성 `Test.ABC.dll`합니다.</span><span class="sxs-lookup"><span data-stu-id="4b206-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b206-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="4b206-121">See also</span></span>

- [<span data-ttu-id="4b206-122">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="4b206-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4b206-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b206-123">-out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)
- [<span data-ttu-id="4b206-124">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="4b206-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
