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
ms.openlocfilehash: cb9242160b684b3c7b90756d7b20811ad162fc30
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043638"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="876ff-102">IManagedObject::GetSerializedBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="876ff-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="876ff-103">이 관리 되는 개체의 문자열 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="876ff-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="876ff-104">구문</span><span class="sxs-lookup"><span data-stu-id="876ff-104">Syntax</span></span>  
  
```  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="876ff-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="876ff-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="876ff-106">[out] 문자열은 직렬화 된 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="876ff-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="876ff-107">설명</span><span class="sxs-lookup"><span data-stu-id="876ff-107">Remarks</span></span>  
 <span data-ttu-id="876ff-108">`GetSerializedBuffer` 클라이언트로 마샬링할 수 있도록 메서드는 개체를 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="876ff-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="876ff-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="876ff-109">Requirements</span></span>  
 <span data-ttu-id="876ff-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="876ff-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="876ff-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="876ff-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="876ff-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="876ff-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="876ff-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="876ff-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="876ff-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="876ff-114">See also</span></span>

- [<span data-ttu-id="876ff-115">IManagedObject 인터페이스</span><span class="sxs-lookup"><span data-stu-id="876ff-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
