---
title: -codepage(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: 59dc1abc3f678a4cf15543c11f9f200ff318ce8f
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65876920"
---
# <a name="-codepage-c-compiler-options"></a><span data-ttu-id="28534-102">-codepage(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="28534-102">-codepage (C# Compiler Options)</span></span>
<span data-ttu-id="28534-103">이 옵션은 필수 페이지가 시스템에 대한 현재 기본 코드 페이지가 아닌 경우 컴파일 중에 사용할 코드 페이지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="28534-103">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28534-104">구문</span><span class="sxs-lookup"><span data-stu-id="28534-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="28534-105">인수</span><span class="sxs-lookup"><span data-stu-id="28534-105">Arguments</span></span>  
 `id`  
 <span data-ttu-id="28534-106">컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="28534-106">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28534-107">주의</span><span class="sxs-lookup"><span data-stu-id="28534-107">Remarks</span></span>  
 <span data-ttu-id="28534-108">컴파일러는 먼저 모든 소스 파일을 UTF-8로 해석하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="28534-108">The compiler will first attempt to interpret all source files as UTF-8.</span></span> <span data-ttu-id="28534-109">소스 코드 파일이 UTF-8 이외의 인코딩에 있고 7비트 ASCII 문자가 아닌 문자를 사용하는 경우 **-codepage** 옵션을 통해 사용할 코드 페이지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="28534-109">If your source code files are in an encoding other than UTF-8 and use characters other than 7-bit ASCII characters, use the **-codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="28534-110">**-codepage**는 컴파일에 포함된 모든 소스 코드 파일에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="28534-110">**-codepage** applies to all source code files in your compilation.</span></span>  
    
 <span data-ttu-id="28534-111">시스템에서 지원되는 코드 페이지를 찾는 방법에 대한 자세한 내용은 [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28534-111">See [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="28534-112">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="28534-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28534-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28534-113">See also</span></span>

- [<span data-ttu-id="28534-114">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="28534-114">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="28534-115">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="28534-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
