---
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 03dc98c45a894304a67765c3e49cd19bbb089c8c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335430"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="62c53-102">-nologo(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62c53-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="62c53-103">컴파일하는 동안 저작권 배너 및 정보 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62c53-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62c53-104">구문</span><span class="sxs-lookup"><span data-stu-id="62c53-104">Syntax</span></span>  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="62c53-105">설명</span><span class="sxs-lookup"><span data-stu-id="62c53-105">Remarks</span></span>  
 <span data-ttu-id="62c53-106">`-nologo`를 지정하면 컴파일러에 저작권 배너가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62c53-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="62c53-107">기본적으로 `-nologo`은 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62c53-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62c53-108">Visual Studio 개발 환경 내에서는 `-nologo` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c53-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62c53-109">예제</span><span class="sxs-lookup"><span data-stu-id="62c53-109">Example</span></span>  
 <span data-ttu-id="62c53-110">다음 코드는 `T2.vb`를 컴파일하고 저작권 배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62c53-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="62c53-111">참조</span><span class="sxs-lookup"><span data-stu-id="62c53-111">See also</span></span>

- [<span data-ttu-id="62c53-112">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="62c53-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="62c53-113">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="62c53-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
