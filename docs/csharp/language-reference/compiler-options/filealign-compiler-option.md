---
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
ms.openlocfilehash: aed8b412ea1580f7dfa4f87333598d76a85b5e64
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "69603016"
---
# <a name="-filealign-c-compiler-options"></a><span data-ttu-id="f5bf1-102">-filealign(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="f5bf1-102">-filealign (C# Compiler Options)</span></span>
<span data-ttu-id="f5bf1-103">**-filealign** 옵션을 사용하여 출력 파일의 섹션 크기를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bf1-103">The **-filealign** option lets you specify the size of sections in your output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5bf1-104">구문</span><span class="sxs-lookup"><span data-stu-id="f5bf1-104">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="f5bf1-105">인수</span><span class="sxs-lookup"><span data-stu-id="f5bf1-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="f5bf1-106">출력 파일의 섹션 크기를 지하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f5bf1-106">A value that specifies the size of sections in the output file.</span></span> <span data-ttu-id="f5bf1-107">유효한 값은 512, 1024, 2048, 4096 및 8192입니다.</span><span class="sxs-lookup"><span data-stu-id="f5bf1-107">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="f5bf1-108">이러한 값은 바이트 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="f5bf1-108">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5bf1-109">설명</span><span class="sxs-lookup"><span data-stu-id="f5bf1-109">Remarks</span></span>  
 <span data-ttu-id="f5bf1-110">각 섹션은 **-filealign** 값의 배수인 경계에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="f5bf1-110">Each section will be aligned on a boundary that is a multiple of the **-filealign** value.</span></span> <span data-ttu-id="f5bf1-111">고정된 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bf1-111">There is no fixed default.</span></span> <span data-ttu-id="f5bf1-112">**-filealign**을 지정하지 않으면 공용언어 런타임에서 컴파일 시간에 기본값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f5bf1-112">If **-filealign** is not specified, the common language runtime picks a default at compile time.</span></span>  
  
 <span data-ttu-id="f5bf1-113">섹션 크기를 지정하면 출력 파일의 크기에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5bf1-113">By specifying the section size, you affect the size of the output file.</span></span> <span data-ttu-id="f5bf1-114">섹션 크기를 수정하면 더 작은 디바이스에서 실행되는 프로그램에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5bf1-114">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
 <span data-ttu-id="f5bf1-115">출력 파일의 섹션에 대한 정보를 확인하려면 [DUMPBIN](/cpp/build/reference/dumpbin-options)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f5bf1-115">Use [DUMPBIN](/cpp/build/reference/dumpbin-options) to see information about sections in your output file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f5bf1-116">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="f5bf1-116">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="f5bf1-117">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f5bf1-117">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="f5bf1-118">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5bf1-118">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="f5bf1-119">**고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5bf1-119">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="f5bf1-120">**파일 맞춤** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5bf1-120">Modify the **File Alignment** property.</span></span>  
  
 <span data-ttu-id="f5bf1-121">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5bf1-121">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5bf1-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5bf1-122">See also</span></span>

- [<span data-ttu-id="f5bf1-123">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="f5bf1-123">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="f5bf1-124">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="f5bf1-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
