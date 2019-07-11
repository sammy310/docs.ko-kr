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
ms.openlocfilehash: 96fee259b31938ddec5820bc1b8d72a96b50c8d8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773888"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="b55be-102">BucketParameters 구조체</span><span class="sxs-lookup"><span data-stu-id="b55be-102">BucketParameters Structure</span></span>
<span data-ttu-id="b55be-103">이벤트와 연결 된 현재 예외에 대 한 이벤트 및 매개 변수 형식 이름을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b55be-104">구문</span><span class="sxs-lookup"><span data-stu-id="b55be-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="b55be-105">멤버</span><span class="sxs-lookup"><span data-stu-id="b55be-105">Members</span></span>  
  
|<span data-ttu-id="b55be-106">멤버</span><span class="sxs-lookup"><span data-stu-id="b55be-106">Member</span></span>|<span data-ttu-id="b55be-107">설명</span><span class="sxs-lookup"><span data-stu-id="b55be-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="b55be-108">`true`를이 구조의 나머지 올바르면; 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="b55be-109">이벤트 유형의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="b55be-110">이벤트에 연결 된 현재 예외에 대 한 매개 변수를 지정 하는 각 문자열의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b55be-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b55be-111">Requirements</span></span>  
 <span data-ttu-id="b55be-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b55be-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b55be-113">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="b55be-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="b55be-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b55be-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b55be-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="b55be-115">See also</span></span>

- [<span data-ttu-id="b55be-116">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="b55be-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
