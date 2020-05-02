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
ms.openlocfilehash: fef2652f591e713140c651a9cb0df1ea9e6236c8
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005592"
---
# <a name="-filealign"></a><span data-ttu-id="5486a-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="5486a-102">-filealign</span></span>
<span data-ttu-id="5486a-103">출력 파일의 섹션에 맞출 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5486a-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5486a-104">구문</span><span class="sxs-lookup"><span data-stu-id="5486a-104">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="5486a-105">인수</span><span class="sxs-lookup"><span data-stu-id="5486a-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="5486a-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="5486a-106">Required.</span></span> <span data-ttu-id="5486a-107">출력 파일에 있는 섹션의 맞춤을 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5486a-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="5486a-108">유효한 값은 512, 1024, 2048, 4096 및 8192입니다.</span><span class="sxs-lookup"><span data-stu-id="5486a-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="5486a-109">이러한 값은 바이트 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="5486a-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5486a-110">설명</span><span class="sxs-lookup"><span data-stu-id="5486a-110">Remarks</span></span>  
 <span data-ttu-id="5486a-111">`-filealign` 옵션을 사용하여 출력 파일에 있는 섹션의 맞춤을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5486a-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="5486a-112">섹션은 코드 또는 데이터를 포함하는 PE(이식 가능한 실행) 파일의 연속 메모리 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="5486a-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="5486a-113">`-filealign` 옵션을 사용하면 비표준 맞춤을 통해 애플리케이션을 컴파일할 수 있습니다. 대부분의 개발자는 이 옵션을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5486a-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="5486a-114">각 섹션은 `-filealign` 값의 배수인 경계에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="5486a-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="5486a-115">고정된 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5486a-115">There is no fixed default.</span></span> <span data-ttu-id="5486a-116">`-filealign`을 지정하지 않으면 컴파일러는 컴파일 시간에 기본값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5486a-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="5486a-117">섹션 크기를 지정하여 출력 파일의 크기에 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5486a-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="5486a-118">섹션 크기를 수정하면 더 작은 디바이스에서 실행되는 프로그램에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5486a-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5486a-119">Visual Studio 개발 환경 내에서는 `-filealign` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5486a-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5486a-120">참조</span><span class="sxs-lookup"><span data-stu-id="5486a-120">See also</span></span>

- [<span data-ttu-id="5486a-121">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="5486a-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
