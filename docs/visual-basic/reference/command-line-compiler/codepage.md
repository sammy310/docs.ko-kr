---
title: -codepage
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: a38fb4be9347b3372b4a459fce2e96b9e38c3a51
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343541"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="08009-102">-codepage(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08009-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="08009-103">컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08009-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08009-104">구문</span><span class="sxs-lookup"><span data-stu-id="08009-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="08009-105">인수</span><span class="sxs-lookup"><span data-stu-id="08009-105">Arguments</span></span>  
  
|<span data-ttu-id="08009-106">용어</span><span class="sxs-lookup"><span data-stu-id="08009-106">Term</span></span>|<span data-ttu-id="08009-107">정의</span><span class="sxs-lookup"><span data-stu-id="08009-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="08009-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="08009-108">Required.</span></span> <span data-ttu-id="08009-109">컴파일러는 `id`에 지정된 코드 페이지를 사용하여 원본 파일의 인코딩을 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="08009-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08009-110">설명</span><span class="sxs-lookup"><span data-stu-id="08009-110">Remarks</span></span>  
 <span data-ttu-id="08009-111">특정 인코딩으로 저장된 소스 코드를 컴파일하려면 `-codepage`를 사용하여 사용할 코드 페이지를 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08009-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="08009-112">`-codepage` 옵션은 컴파일에 있는 모든 소스 코드 파일에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08009-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="08009-113">자세한 내용은 [.NET Framework의 문자 인코딩](../../../standard/base-types/character-encoding.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08009-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="08009-114">소스 코드 파일이 시그니처와 함께 현재 ANSI 코드 페이지, 유니코드 또는 UTF-8을 사용하여 저장된 경우에는 `-codepage` 옵션이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08009-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="08009-115">사용자가 **인코딩** 대화 상자에서 다른 인코딩을 지정하지 않는 한 Visual Studio는 기본적으로 현재 ANSI 코드 페이지를 사용하여 모든 소스 코드 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="08009-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="08009-116">Visual Studio는 **인코딩** 대화 상자를 사용하여 다른 코드 페이지로 저장된 소스 코드 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="08009-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08009-117">Visual Studio 개발 환경 내에서는 `-codepage` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08009-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08009-118">참조</span><span class="sxs-lookup"><span data-stu-id="08009-118">See also</span></span>

- [<span data-ttu-id="08009-119">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="08009-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
