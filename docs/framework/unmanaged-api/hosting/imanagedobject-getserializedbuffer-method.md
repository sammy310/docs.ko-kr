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
ms.openlocfilehash: 4a55ae265230c4da3cc0a19b06a7597be8661beb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103255"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="bfdf9-102">IManagedObject::GetSerializedBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="bfdf9-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="bfdf9-103">이 관리 되는 개체의 문자열 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfdf9-104">구문</span><span class="sxs-lookup"><span data-stu-id="bfdf9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfdf9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bfdf9-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="bfdf9-106">제한이 Serialize 된 개체에 해당 하는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfdf9-107">주의</span><span class="sxs-lookup"><span data-stu-id="bfdf9-107">Remarks</span></span>  
 <span data-ttu-id="bfdf9-108">`GetSerializedBuffer` 메서드는 개체를 클라이언트에 마샬링할 수 있도록 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfdf9-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bfdf9-109">Requirements</span></span>  
 <span data-ttu-id="bfdf9-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfdf9-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bfdf9-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bfdf9-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bfdf9-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfdf9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfdf9-114">참조</span><span class="sxs-lookup"><span data-stu-id="bfdf9-114">See also</span></span>

- [<span data-ttu-id="bfdf9-115">IManagedObject 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bfdf9-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
