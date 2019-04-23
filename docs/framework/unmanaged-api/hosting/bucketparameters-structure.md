---
title: BucketParameters 구조체
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5998ce684726b2386d8f1e05eb7eaeccf455747c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110458"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="9edad-102">BucketParameters 구조체</span><span class="sxs-lookup"><span data-stu-id="9edad-102">BucketParameters Structure</span></span>
<span data-ttu-id="9edad-103">이벤트와 연결 된 현재 예외에 대 한 이벤트 및 매개 변수 형식 이름을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9edad-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9edad-104">구문</span><span class="sxs-lookup"><span data-stu-id="9edad-104">Syntax</span></span>  
  
```  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="9edad-105">멤버</span><span class="sxs-lookup"><span data-stu-id="9edad-105">Members</span></span>  
  
|<span data-ttu-id="9edad-106">멤버</span><span class="sxs-lookup"><span data-stu-id="9edad-106">Member</span></span>|<span data-ttu-id="9edad-107">설명</span><span class="sxs-lookup"><span data-stu-id="9edad-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="9edad-108">`true`를이 구조의 나머지 올바르면; 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="9edad-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="9edad-109">이벤트 유형의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9edad-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="9edad-110">이벤트에 연결 된 현재 예외에 대 한 매개 변수를 지정 하는 각 문자열의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9edad-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9edad-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9edad-111">Requirements</span></span>  
 <span data-ttu-id="9edad-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9edad-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9edad-113">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="9edad-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="9edad-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9edad-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9edad-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="9edad-115">See also</span></span>

- [<span data-ttu-id="9edad-116">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="9edad-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
