---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 07e1718554b158635b9d8b04958834e804e1fe9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964386"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="da3cf-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da3cf-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="da3cf-103">컴파일하는 동안 저작권 배너 및 정보 메시지를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da3cf-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da3cf-104">구문</span><span class="sxs-lookup"><span data-stu-id="da3cf-104">Syntax</span></span>  
  
```  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="da3cf-105">설명</span><span class="sxs-lookup"><span data-stu-id="da3cf-105">Remarks</span></span>  
 <span data-ttu-id="da3cf-106">을 지정 `-nologo`하는 경우 컴파일러는 저작권 배너를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da3cf-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="da3cf-107">기본적으로 `-nologo`은 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da3cf-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da3cf-108">이 `-nologo` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da3cf-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da3cf-109">예제</span><span class="sxs-lookup"><span data-stu-id="da3cf-109">Example</span></span>  
 <span data-ttu-id="da3cf-110">다음 코드는 저작권 `T2.vb` 배너를 컴파일하고 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da3cf-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="da3cf-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="da3cf-111">See also</span></span>

- [<span data-ttu-id="da3cf-112">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="da3cf-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="da3cf-113">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="da3cf-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
