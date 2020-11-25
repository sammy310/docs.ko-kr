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
ms.openlocfilehash: 159ece09ae0b6a67780639da8aae8c0e4b412bb8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730697"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="3d450-102">IManagedObject::GetSerializedBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="3d450-102">IManagedObject::GetSerializedBuffer Method</span></span>

<span data-ttu-id="3d450-103">이 관리 되는 개체의 문자열 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d450-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d450-104">구문</span><span class="sxs-lookup"><span data-stu-id="3d450-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d450-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3d450-105">Parameters</span></span>  

 `pBSTR`  
 <span data-ttu-id="3d450-106">제한이 Serialize 된 개체에 해당 하는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3d450-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d450-107">설명</span><span class="sxs-lookup"><span data-stu-id="3d450-107">Remarks</span></span>  

 <span data-ttu-id="3d450-108">`GetSerializedBuffer`메서드는 클라이언트에 마샬링될 수 있도록 개체를 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d450-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d450-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d450-109">Requirements</span></span>  

 <span data-ttu-id="3d450-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d450-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d450-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3d450-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d450-112">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d450-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d450-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d450-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d450-114">참조</span><span class="sxs-lookup"><span data-stu-id="3d450-114">See also</span></span>

- [<span data-ttu-id="3d450-115">IManagedObject 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d450-115">IManagedObject Interface</span></span>](imanagedobject-interface.md)
