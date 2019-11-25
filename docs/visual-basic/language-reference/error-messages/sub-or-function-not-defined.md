---
title: Sub 또는 Function이 정의되지 않았습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 8b81460eccb6be8baa2ea7bc68d0f80c9d16398e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349571"
---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="4d05a-102">Sub 또는 Function이 정의되지 않았습니다(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="4d05a-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="4d05a-103">A `Sub` or `Function` must be defined in order to be called.</span><span class="sxs-lookup"><span data-stu-id="4d05a-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="4d05a-104">이 오류가 발생하는 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d05a-104">Possible causes of this error include:</span></span>  
  
- <span data-ttu-id="4d05a-105">Misspelling the procedure name.</span><span class="sxs-lookup"><span data-stu-id="4d05a-105">Misspelling the procedure name.</span></span>  
  
- <span data-ttu-id="4d05a-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span><span class="sxs-lookup"><span data-stu-id="4d05a-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
- <span data-ttu-id="4d05a-107">Specifying a procedure that is not visible to the calling procedure.</span><span class="sxs-lookup"><span data-stu-id="4d05a-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
- <span data-ttu-id="4d05a-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span><span class="sxs-lookup"><span data-stu-id="4d05a-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4d05a-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="4d05a-109">To correct this error</span></span>  
  
1. <span data-ttu-id="4d05a-110">Make sure that the procedure name is spelled correctly.</span><span class="sxs-lookup"><span data-stu-id="4d05a-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2. <span data-ttu-id="4d05a-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span><span class="sxs-lookup"><span data-stu-id="4d05a-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="4d05a-112">If it does not appear, click the **Browse** button to search for it.</span><span class="sxs-lookup"><span data-stu-id="4d05a-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="4d05a-113">Select the check box to the left of the project name, and then click **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d05a-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="4d05a-114">Check the name of the routine.</span><span class="sxs-lookup"><span data-stu-id="4d05a-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d05a-115">참조</span><span class="sxs-lookup"><span data-stu-id="4d05a-115">See also</span></span>

- [<span data-ttu-id="4d05a-116">오류 형식</span><span class="sxs-lookup"><span data-stu-id="4d05a-116">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="4d05a-117">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="4d05a-117">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="4d05a-118">Sub 문</span><span class="sxs-lookup"><span data-stu-id="4d05a-118">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="4d05a-119">Function 문</span><span class="sxs-lookup"><span data-stu-id="4d05a-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
