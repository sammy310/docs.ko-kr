---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: bb64a468f67745b80b47b42c4fac18852279035d
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005431"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="fa209-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa209-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="fa209-103">컴파일하는 동안 저작권 배너 및 정보 메시지를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa209-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa209-104">구문</span><span class="sxs-lookup"><span data-stu-id="fa209-104">Syntax</span></span>  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="fa209-105">설명</span><span class="sxs-lookup"><span data-stu-id="fa209-105">Remarks</span></span>  
 <span data-ttu-id="fa209-106">@No__t-0을 지정 하는 경우 컴파일러는 저작권 배너를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa209-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="fa209-107">기본적으로 `-nologo`은 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa209-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa209-108">@No__t-0 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa209-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa209-109">예제</span><span class="sxs-lookup"><span data-stu-id="fa209-109">Example</span></span>  
 <span data-ttu-id="fa209-110">다음 코드는 `T2.vb`을 컴파일하고 저작권 배너를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa209-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa209-111">참조</span><span class="sxs-lookup"><span data-stu-id="fa209-111">See also</span></span>

- [<span data-ttu-id="fa209-112">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="fa209-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="fa209-113">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="fa209-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
