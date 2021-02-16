---
description: "자세한 정보: ' Object ' 형식의 인수를 사용 하는 경우 ' FileGet ' 대신 ' FileGetObject ' 사용"
title: "'Object' 형식의 인수를 사용하는 경우 'FileGet' 대신 'FileGetObject'를 사용합니다."
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 4481fdced961cacf0e652c141601efa13bec776b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471164"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a><span data-ttu-id="c01de-103">'Object' 형식의 인수를 사용하는 경우 'FileGet' 대신 'FileGetObject'를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c01de-103">Use 'FileGetObject' instead of 'FileGet' when using argument of type 'Object'</span></span>

<span data-ttu-id="c01de-104">`FileGet` 메서드는 `Object`형식의 인수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c01de-104">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="c01de-105">모호성을 피하기 위해`FileGetObject` 대신 `FileGet` 를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c01de-105">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="c01de-106">`My.Computer.Filesystem`에서 제공하는 기능이 `FileGet` 또는 `FileGetObject`보다 사용하기 쉽고 성능이 뛰어납니다.</span><span class="sxs-lookup"><span data-stu-id="c01de-106">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c01de-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c01de-107">To correct this error</span></span>  
  
1. <span data-ttu-id="c01de-108">`FileGet`을 `FileGetObject`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c01de-108">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2. <span data-ttu-id="c01de-109">`Object` 인수를 더 구체적인 형식으로 캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="c01de-109">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c01de-110">추가 정보</span><span class="sxs-lookup"><span data-stu-id="c01de-110">See also</span></span>

- [<span data-ttu-id="c01de-111">My.user. 컴퓨터 파일 시스템</span><span class="sxs-lookup"><span data-stu-id="c01de-111">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
