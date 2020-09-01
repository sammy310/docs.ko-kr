---
description: -filealign(C# 컴파일러 옵션)
title: -filealign(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /filealign
helpviewer_keywords:
- /alignment compiler option [C#]
- filealign compiler option [C#]
- -filealign compiler option [C#]
- /sections compiler option [C#]
- alignment compiler option [C#]
- sections compiler option [C#]
- -sections compiler option [C#]
- /filealign compiler option [C#]
- file sharing [C#]
- -alignment compiler option [C#]
- section alignment [C#]
ms.assetid: 15cf1c98-3798-4ced-9f08-60619308a073
ms.openlocfilehash: d4abe6c3825de211d737f402a745c8953adca4b8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125711"
---
# <a name="-filealign-c-compiler-options"></a><span data-ttu-id="f6a30-103">-filealign(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="f6a30-103">-filealign (C# Compiler Options)</span></span>
<span data-ttu-id="f6a30-104">**-filealign** 옵션을 사용하여 출력 파일의 섹션 크기를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a30-104">The **-filealign** option lets you specify the size of sections in your output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6a30-105">구문</span><span class="sxs-lookup"><span data-stu-id="f6a30-105">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="f6a30-106">인수</span><span class="sxs-lookup"><span data-stu-id="f6a30-106">Arguments</span></span>  
 `number`  
 <span data-ttu-id="f6a30-107">출력 파일의 섹션 크기를 지하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f6a30-107">A value that specifies the size of sections in the output file.</span></span> <span data-ttu-id="f6a30-108">유효한 값은 512, 1024, 2048, 4096 및 8192입니다.</span><span class="sxs-lookup"><span data-stu-id="f6a30-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="f6a30-109">이러한 값은 바이트 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="f6a30-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6a30-110">설명</span><span class="sxs-lookup"><span data-stu-id="f6a30-110">Remarks</span></span>  
 <span data-ttu-id="f6a30-111">각 섹션은 **-filealign** 값의 배수인 경계에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="f6a30-111">Each section will be aligned on a boundary that is a multiple of the **-filealign** value.</span></span> <span data-ttu-id="f6a30-112">고정된 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a30-112">There is no fixed default.</span></span> <span data-ttu-id="f6a30-113">**-filealign**을 지정하지 않으면 공용언어 런타임에서 컴파일 시간에 기본값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a30-113">If **-filealign** is not specified, the common language runtime picks a default at compile time.</span></span>  
  
 <span data-ttu-id="f6a30-114">섹션 크기를 지정하면 출력 파일의 크기에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6a30-114">By specifying the section size, you affect the size of the output file.</span></span> <span data-ttu-id="f6a30-115">섹션 크기를 수정하면 더 작은 디바이스에서 실행되는 프로그램에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6a30-115">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
 <span data-ttu-id="f6a30-116">출력 파일의 섹션에 대한 정보를 확인하려면 [DUMPBIN](/cpp/build/reference/dumpbin-options)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f6a30-116">Use [DUMPBIN](/cpp/build/reference/dumpbin-options) to see information about sections in your output file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f6a30-117">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="f6a30-117">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="f6a30-118">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f6a30-118">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="f6a30-119">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a30-119">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="f6a30-120">**고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a30-120">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="f6a30-121">**파일 맞춤** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f6a30-121">Modify the **File Alignment** property.</span></span>  
  
 <span data-ttu-id="f6a30-122">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f6a30-122">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6a30-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6a30-123">See also</span></span>

- [<span data-ttu-id="f6a30-124">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="f6a30-124">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="f6a30-125">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="f6a30-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
