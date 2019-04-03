---
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
ms.openlocfilehash: 9a844515a4596064937762ac05b850463f1b5e14
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819179"
---
# <a name="-filealign"></a><span data-ttu-id="b80ed-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="b80ed-102">-filealign</span></span>
<span data-ttu-id="b80ed-103">출력 파일의 섹션에 맞출 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b80ed-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b80ed-104">구문</span><span class="sxs-lookup"><span data-stu-id="b80ed-104">Syntax</span></span>  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="b80ed-105">인수</span><span class="sxs-lookup"><span data-stu-id="b80ed-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="b80ed-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b80ed-106">Required.</span></span> <span data-ttu-id="b80ed-107">출력 파일의 섹션 맞춤을 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b80ed-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="b80ed-108">유효한 값은 512, 1024, 2048, 4096 및 8192입니다.</span><span class="sxs-lookup"><span data-stu-id="b80ed-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="b80ed-109">이러한 값은 바이트 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="b80ed-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b80ed-110">설명</span><span class="sxs-lookup"><span data-stu-id="b80ed-110">Remarks</span></span>  
 <span data-ttu-id="b80ed-111">사용할 수는 `-filealign` 출력 파일의 섹션 맞춤을 지정 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="b80ed-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="b80ed-112">섹션은 코드 또는 데이터를 포함 하는 PE (이식 가능) 파일의 연속 된 메모리 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="b80ed-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="b80ed-113">`-filealign` 옵션 비표준 맞춤을 사용 하 여 응용 프로그램을 컴파일할 수 있습니다; 대부분의 개발자가이 옵션을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b80ed-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="b80ed-114">각 섹션의 배수인 경계에 정렬 되는 `-filealign` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b80ed-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="b80ed-115">고정된 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b80ed-115">There is no fixed default.</span></span> <span data-ttu-id="b80ed-116">경우 `-filealign` , 지정 하지 않으면 컴파일러가 컴파일 시간에 기본값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b80ed-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="b80ed-117">섹션 크기를 지정 하 여 출력 파일의 크기를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b80ed-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="b80ed-118">섹션 크기를 수정하면 더 작은 디바이스에서 실행되는 프로그램에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b80ed-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b80ed-119">`-filealign` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b80ed-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b80ed-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="b80ed-120">See also</span></span>

- [<span data-ttu-id="b80ed-121">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="b80ed-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
