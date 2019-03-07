---
title: EndMerge 메서드
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d4b102485db0199f748f6c5b6c4ab40d21429e9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494413"
---
# <a name="endmerge-method"></a><span data-ttu-id="598ad-102">EndMerge 메서드</span><span class="sxs-lookup"><span data-stu-id="598ad-102">EndMerge Method</span></span>
<span data-ttu-id="598ad-103">내보내기 범위에 모든 사용자 지정 특성 집합이 병합 된 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="598ad-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="598ad-104">구문</span><span class="sxs-lookup"><span data-stu-id="598ad-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="598ad-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="598ad-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="598ad-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="598ad-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="598ad-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="598ad-107">Return Value</span></span>  
 <span data-ttu-id="598ad-108">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="598ad-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="598ad-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="598ad-109">Requirements</span></span>  
 <span data-ttu-id="598ad-110">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="598ad-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="598ad-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="598ad-111">See also</span></span>
- [<span data-ttu-id="598ad-112">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="598ad-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="598ad-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="598ad-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="598ad-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="598ad-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
