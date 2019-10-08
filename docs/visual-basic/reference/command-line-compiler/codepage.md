---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: e4cdc27ab021fe055f157b78946538f2b76870e1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002365"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="2779e-102">-codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2779e-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="2779e-103">컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2779e-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2779e-104">구문</span><span class="sxs-lookup"><span data-stu-id="2779e-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="2779e-105">인수</span><span class="sxs-lookup"><span data-stu-id="2779e-105">Arguments</span></span>  
  
|<span data-ttu-id="2779e-106">용어</span><span class="sxs-lookup"><span data-stu-id="2779e-106">Term</span></span>|<span data-ttu-id="2779e-107">정의</span><span class="sxs-lookup"><span data-stu-id="2779e-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="2779e-108">필수.</span><span class="sxs-lookup"><span data-stu-id="2779e-108">Required.</span></span> <span data-ttu-id="2779e-109">컴파일러는 `id`으로 지정 된 코드 페이지를 사용 하 여 소스 파일의 인코딩을 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="2779e-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2779e-110">설명</span><span class="sxs-lookup"><span data-stu-id="2779e-110">Remarks</span></span>  
 <span data-ttu-id="2779e-111">특정 인코딩으로 저장 된 소스 코드를 컴파일하려면 `-codepage`을 사용 하 여 사용할 코드 페이지를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2779e-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="2779e-112">@No__t-0 옵션은 컴파일의 모든 소스 코드 파일에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2779e-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="2779e-113">자세한 내용은 [.NET Framework의 문자 인코딩](../../../standard/base-types/character-encoding.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2779e-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="2779e-114">소스 코드 파일이 시그니처와 함께 현재 ANSI 코드 페이지, 유니코드 또는 u t f-8을 사용 하 여 저장 된 경우에는 `-codepage` 옵션이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2779e-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="2779e-115">사용자가 **인코딩** 대화 상자에서 다른 인코딩을 지정 하지 않는 한 Visual Studio는 기본적으로 현재 ANSI 코드 페이지를 사용 하 여 모든 소스 코드 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2779e-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="2779e-116">Visual Studio는 **인코딩** 대화 상자를 사용 하 여 다른 코드 페이지로 저장 된 소스 코드 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2779e-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2779e-117">@No__t-0 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2779e-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2779e-118">참조</span><span class="sxs-lookup"><span data-stu-id="2779e-118">See also</span></span>

- [<span data-ttu-id="2779e-119">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="2779e-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
