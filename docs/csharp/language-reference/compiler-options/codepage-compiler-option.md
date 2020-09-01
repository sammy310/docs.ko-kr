---
description: -codepage(C# 컴파일러 옵션)
title: -codepage(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: 4c812314ed9c1abcd7d2f34b2281140175621312
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125958"
---
# <a name="-codepage-c-compiler-options"></a><span data-ttu-id="d83fa-103">-codepage(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="d83fa-103">-codepage (C# Compiler Options)</span></span>
<span data-ttu-id="d83fa-104">이 옵션은 필수 페이지가 시스템에 대한 현재 기본 코드 페이지가 아닌 경우 컴파일 중에 사용할 코드 페이지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d83fa-104">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d83fa-105">구문</span><span class="sxs-lookup"><span data-stu-id="d83fa-105">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="d83fa-106">인수</span><span class="sxs-lookup"><span data-stu-id="d83fa-106">Arguments</span></span>  
 `id`  
 <span data-ttu-id="d83fa-107">컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d83fa-107">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d83fa-108">설명</span><span class="sxs-lookup"><span data-stu-id="d83fa-108">Remarks</span></span>  
 <span data-ttu-id="d83fa-109">컴파일러는 먼저 모든 소스 파일을 UTF-8로 해석하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d83fa-109">The compiler will first attempt to interpret all source files as UTF-8.</span></span> <span data-ttu-id="d83fa-110">소스 코드 파일이 UTF-8 이외의 인코딩에 있고 7비트 ASCII 문자가 아닌 문자를 사용하는 경우 **-codepage** 옵션을 통해 사용할 코드 페이지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d83fa-110">If your source code files are in an encoding other than UTF-8 and use characters other than 7-bit ASCII characters, use the **-codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="d83fa-111">**-codepage**는 컴파일에 포함된 모든 소스 코드 파일에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d83fa-111">**-codepage** applies to all source code files in your compilation.</span></span>  

 <span data-ttu-id="d83fa-112">시스템에서 지원되는 코드 페이지를 찾는 방법에 대한 자세한 내용은 [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d83fa-112">See [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="d83fa-113">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d83fa-113">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d83fa-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d83fa-114">See also</span></span>

- [<span data-ttu-id="d83fa-115">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="d83fa-115">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="d83fa-116">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="d83fa-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
