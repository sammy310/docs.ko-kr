---
description: '자세한 정보: 잘못 된 파일 이름 또는 숫자'
title: 파일 이름 또는 번호가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 6e568a721fb3606c5b4bc046041c9d6f24b6d126
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797070"
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="23783-103">파일 이름 또는 번호가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="23783-103">Bad file name or number</span></span>

<span data-ttu-id="23783-104">지정 된 파일에 액세스 하는 동안 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="23783-104">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="23783-105">이 오류는 다음과 같은 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23783-105">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="23783-106">문이 문에 지정 되지 않았거나 `FileOpen` 문에 지정 되었지만 이후에 종결 된 파일 이름 또는 번호가 포함 된 파일을 참조 합니다 `FileOpen` .</span><span class="sxs-lookup"><span data-stu-id="23783-106">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
- <span data-ttu-id="23783-107">문이 파일 번호 범위를 벗어난 번호를 사용 하는 파일을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="23783-107">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
- <span data-ttu-id="23783-108">문이 잘못 된 파일 이름 또는 번호를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="23783-108">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="23783-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="23783-109">To correct this error</span></span>  
  
1. <span data-ttu-id="23783-110">문에 파일 이름이 지정 되어 있는지 확인 `FileOpen` 합니다.</span><span class="sxs-lookup"><span data-stu-id="23783-110">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="23783-111">`FileClose`인수 없이 문을 호출 하면 열려 있는 모든 파일이 실수로 닫혀 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23783-111">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2. <span data-ttu-id="23783-112">코드에서 알고리즘 방식으로 파일 번호를 생성 하는 경우 번호가 올바른지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="23783-112">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3. <span data-ttu-id="23783-113">파일 이름을 확인 하 여 운영 체제 규칙을 준수 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="23783-113">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23783-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23783-114">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [<span data-ttu-id="23783-115">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="23783-115">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
