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
ms.openlocfilehash: 4d9de489bdeb0ab506f56ff08f4afb4cf6d0ab4f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178282"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="30c99-102">BucketParameters 구조체</span><span class="sxs-lookup"><span data-stu-id="30c99-102">BucketParameters Structure</span></span>
<span data-ttu-id="30c99-103">이벤트의 형식 이름과 이벤트와 연결된 현재 예외에 대한 매개 변수를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="30c99-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30c99-104">구문</span><span class="sxs-lookup"><span data-stu-id="30c99-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="30c99-105">구성원</span><span class="sxs-lookup"><span data-stu-id="30c99-105">Members</span></span>  
  
|<span data-ttu-id="30c99-106">멤버</span><span class="sxs-lookup"><span data-stu-id="30c99-106">Member</span></span>|<span data-ttu-id="30c99-107">Description</span><span class="sxs-lookup"><span data-stu-id="30c99-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="30c99-108">`true`이 구조의 나머지 가 유효한 경우; 그렇지 `false`않으면 .</span><span class="sxs-lookup"><span data-stu-id="30c99-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="30c99-109">이벤트 유형의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="30c99-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="30c99-110">이벤트와 관련된 현재 예외에 대한 매개 변수를 지정하는 각각의 문자열 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="30c99-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="30c99-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="30c99-111">Requirements</span></span>  
 <span data-ttu-id="30c99-112">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30c99-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30c99-113">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="30c99-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="30c99-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30c99-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c99-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30c99-115">See also</span></span>

- [<span data-ttu-id="30c99-116">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="30c99-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
