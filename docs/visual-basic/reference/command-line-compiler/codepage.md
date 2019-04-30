---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: fda75383435fdff718d1d50bc8583afc9858e7e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944705"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="0d12d-102">-codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d12d-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="0d12d-103">컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d12d-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d12d-104">구문</span><span class="sxs-lookup"><span data-stu-id="0d12d-104">Syntax</span></span>  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="0d12d-105">인수</span><span class="sxs-lookup"><span data-stu-id="0d12d-105">Arguments</span></span>  
  
|<span data-ttu-id="0d12d-106">용어</span><span class="sxs-lookup"><span data-stu-id="0d12d-106">Term</span></span>|<span data-ttu-id="0d12d-107">정의</span><span class="sxs-lookup"><span data-stu-id="0d12d-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="0d12d-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="0d12d-108">Required.</span></span> <span data-ttu-id="0d12d-109">컴파일러에서 지정한 코드 페이지를 사용 하 여 `id` 원본 파일의 인코딩을 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d12d-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d12d-110">설명</span><span class="sxs-lookup"><span data-stu-id="0d12d-110">Remarks</span></span>  
 <span data-ttu-id="0d12d-111">특정 인코딩을 사용 하 여 저장 된 소스 코드를 컴파일하는 데 사용할 수 있습니다 `-codepage` 사용할 코드 페이지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d12d-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="0d12d-112">`-codepage` 옵션 컴파일에서 모든 소스 코드 파일에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d12d-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="0d12d-113">자세한 내용은 [.NET Framework의 문자 인코딩](../../../standard/base-types/character-encoding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0d12d-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="0d12d-114">`-codepage` 옵션의 현재 ANSI 코드 페이지, Unicode 또는 u t F-8을 사용 하 여 서명을 사용 하 여 소스 코드 파일을 저장 한 경우에 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d12d-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="0d12d-115">Visual Studio 저장 모든 소스 코드 파일의 현재 ANSI 코드 페이지를 사용 하 여 기본적으로 사용자에서 다른 인코딩을 지정 하지 않는 경우는 **Encoding** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="0d12d-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="0d12d-116">Visual Studio에서 사용 하는 **Encoding** 대화 상자를 다른 코드 페이지를 사용 하 여 저장 하는 소스 코드 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0d12d-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d12d-117">`-codepage` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0d12d-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d12d-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="0d12d-118">See also</span></span>

- [<span data-ttu-id="0d12d-119">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="0d12d-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
