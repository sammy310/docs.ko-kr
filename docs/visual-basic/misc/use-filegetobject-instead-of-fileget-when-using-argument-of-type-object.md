---
title: "'Object' 형식의 인수를 사용하는 경우 'FileGet' 대신 'FileGetObject'를 사용합니다."
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 318a0772a99aa86d9a4633e6021f77616a43fc7e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059407"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a><span data-ttu-id="8ed8e-102">'Object' 형식의 인수를 사용하는 경우 'FileGet' 대신 'FileGetObject'를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8e-102">Use 'FileGetObject' instead of 'FileGet' when using argument of type 'Object'</span></span>

<span data-ttu-id="8ed8e-103">`FileGet` 메서드는 `Object`형식의 인수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8e-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="8ed8e-104">모호성을 피하기 위해`FileGetObject` 대신 `FileGet` 를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8e-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="8ed8e-105">`My.Computer.Filesystem`에서 제공하는 기능이 `FileGet` 또는 `FileGetObject`보다 사용하기 쉽고 성능이 뛰어납니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8e-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8ed8e-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="8ed8e-106">To correct this error</span></span>  
  
1. <span data-ttu-id="8ed8e-107">`FileGet`을 `FileGetObject`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8e-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2. <span data-ttu-id="8ed8e-108">`Object` 인수를 더 구체적인 형식으로 캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8e-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ed8e-109">참조</span><span class="sxs-lookup"><span data-stu-id="8ed8e-109">See also</span></span>

- [<span data-ttu-id="8ed8e-110">My.user. 컴퓨터 파일 시스템</span><span class="sxs-lookup"><span data-stu-id="8ed8e-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
