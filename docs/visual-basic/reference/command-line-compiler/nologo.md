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
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335430"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="366db-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="366db-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="366db-103">Suppresses display of the copyright banner and informational messages during compilation.</span><span class="sxs-lookup"><span data-stu-id="366db-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="366db-104">구문</span><span class="sxs-lookup"><span data-stu-id="366db-104">Syntax</span></span>  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="366db-105">주의</span><span class="sxs-lookup"><span data-stu-id="366db-105">Remarks</span></span>  
 <span data-ttu-id="366db-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span><span class="sxs-lookup"><span data-stu-id="366db-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="366db-107">기본적으로 `-nologo`은 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="366db-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="366db-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span><span class="sxs-lookup"><span data-stu-id="366db-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="366db-109">예제</span><span class="sxs-lookup"><span data-stu-id="366db-109">Example</span></span>  
 <span data-ttu-id="366db-110">The following code compiles `T2.vb` and does not display a copyright banner.</span><span class="sxs-lookup"><span data-stu-id="366db-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="366db-111">참조</span><span class="sxs-lookup"><span data-stu-id="366db-111">See also</span></span>

- [<span data-ttu-id="366db-112">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="366db-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="366db-113">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="366db-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
