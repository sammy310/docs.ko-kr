---
title: IManagedObject::GetSerializedBuffer 메서드
ms.date: 03/30/2017
api_name:
- IManagedObject.GetSerializedBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65ac35e254368b53ac2751e84be7dfe052fa0b53
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749076"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="c4b29-102">IManagedObject::GetSerializedBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="c4b29-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="c4b29-103">이 관리 되는 개체의 문자열 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c4b29-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4b29-104">구문</span><span class="sxs-lookup"><span data-stu-id="c4b29-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4b29-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c4b29-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="c4b29-106">[out] 문자열은 직렬화 된 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c4b29-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4b29-107">설명</span><span class="sxs-lookup"><span data-stu-id="c4b29-107">Remarks</span></span>  
 <span data-ttu-id="c4b29-108">`GetSerializedBuffer` 클라이언트로 마샬링할 수 있도록 메서드는 개체를 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b29-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4b29-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c4b29-109">Requirements</span></span>  
 <span data-ttu-id="c4b29-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c4b29-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4b29-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c4b29-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4b29-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c4b29-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4b29-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4b29-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b29-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="c4b29-114">See also</span></span>

- [<span data-ttu-id="c4b29-115">IManagedObject 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c4b29-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
