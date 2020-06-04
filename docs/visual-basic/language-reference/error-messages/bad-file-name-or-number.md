---
title: 파일 이름 또는 번호가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 11e866d9a8da7ad1ecc5f788fc31f6ac96d32f2c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409831"
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="755f3-102">파일 이름 또는 번호가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="755f3-102">Bad file name or number</span></span>
<span data-ttu-id="755f3-103">지정 된 파일에 액세스 하는 동안 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="755f3-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="755f3-104">이 오류는 다음과 같은 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="755f3-104">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="755f3-105">문이 문에 지정 되지 않았거나 `FileOpen` 문에 지정 되었지만 이후에 종결 된 파일 이름 또는 번호가 포함 된 파일을 참조 합니다 `FileOpen` .</span><span class="sxs-lookup"><span data-stu-id="755f3-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
- <span data-ttu-id="755f3-106">문이 파일 번호 범위를 벗어난 번호를 사용 하는 파일을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="755f3-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
- <span data-ttu-id="755f3-107">문이 잘못 된 파일 이름 또는 번호를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="755f3-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="755f3-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="755f3-108">To correct this error</span></span>  
  
1. <span data-ttu-id="755f3-109">문에 파일 이름이 지정 되어 있는지 확인 `FileOpen` 합니다.</span><span class="sxs-lookup"><span data-stu-id="755f3-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="755f3-110">`FileClose`인수 없이 문을 호출 하면 열려 있는 모든 파일이 실수로 닫혀 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="755f3-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2. <span data-ttu-id="755f3-111">코드에서 알고리즘 방식으로 파일 번호를 생성 하는 경우 번호가 올바른지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="755f3-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3. <span data-ttu-id="755f3-112">파일 이름을 확인 하 여 운영 체제 규칙을 준수 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="755f3-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="755f3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="755f3-113">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [<span data-ttu-id="755f3-114">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="755f3-114">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
