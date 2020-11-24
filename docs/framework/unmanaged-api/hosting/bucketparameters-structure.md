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
ms.openlocfilehash: 8b54cb30ec96ad0fb7851af6f2d465fe771886ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677858"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="77a9a-102">BucketParameters 구조체</span><span class="sxs-lookup"><span data-stu-id="77a9a-102">BucketParameters Structure</span></span>

<span data-ttu-id="77a9a-103">이벤트의 형식 이름 및 이벤트와 연결 된 현재 예외에 대 한 매개 변수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a9a-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77a9a-104">구문</span><span class="sxs-lookup"><span data-stu-id="77a9a-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="77a9a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="77a9a-105">Members</span></span>  
  
|<span data-ttu-id="77a9a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="77a9a-106">Member</span></span>|<span data-ttu-id="77a9a-107">설명</span><span class="sxs-lookup"><span data-stu-id="77a9a-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="77a9a-108">`true`이 구조체의 나머지가 유효 하면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="77a9a-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="77a9a-109">이벤트 유형의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="77a9a-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="77a9a-110">각각 이벤트와 연결 된 현재 예외에 대 한 매개 변수를 지정 하는 문자열의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="77a9a-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77a9a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="77a9a-111">Requirements</span></span>  

 <span data-ttu-id="77a9a-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77a9a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77a9a-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="77a9a-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="77a9a-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77a9a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77a9a-115">참조</span><span class="sxs-lookup"><span data-stu-id="77a9a-115">See also</span></span>

- [<span data-ttu-id="77a9a-116">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="77a9a-116">Hosting Structures</span></span>](hosting-structures.md)
