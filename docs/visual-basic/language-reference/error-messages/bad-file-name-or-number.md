---
title: 파일 이름 또는 번호가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 2e5d4a3ddd66df85dc4758e22b36ac1ed495659a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59322162"
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="a0a3f-102">파일 이름 또는 번호가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3f-102">Bad file name or number</span></span>
<span data-ttu-id="a0a3f-103">지정한 파일에 액세스 하는 동안 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3f-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="a0a3f-104">이 오류에 대 한 가능한 원인 중:</span><span class="sxs-lookup"><span data-stu-id="a0a3f-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="a0a3f-105">문에서 참조에서 지정 되지 않은 파일 이름 또는 번호를 사용 하 여 파일에는 `FileOpen` 문이나는에 지정 된을 `FileOpen` 문을 하지만 이후에 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3f-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
-   <span data-ttu-id="a0a3f-106">문이 파일 번호의 범위를 벗어난 숫자로 파일을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3f-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
-   <span data-ttu-id="a0a3f-107">문에 파일 이름 또는 유효 하지 않은 숫자를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3f-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a0a3f-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a0a3f-108">To correct this error</span></span>  
  
1. <span data-ttu-id="a0a3f-109">파일 이름에 지정 해야는 `FileOpen` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3f-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="a0a3f-110">호출 하는 경우는 `FileClose` 문 인수 없이 있습니다 닫힐 수 열려 있는 모든 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3f-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2. <span data-ttu-id="a0a3f-111">코드를 생성할 경우 파일 번호 알고리즘 방식으로 숫자 올바른지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3f-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3. <span data-ttu-id="a0a3f-112">운영 체제 규칙을 준수 하는지 확인 하려면 파일 이름을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a3f-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a3f-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="a0a3f-113">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [<span data-ttu-id="a0a3f-114">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="a0a3f-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
