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
ms.openlocfilehash: c68ec0b41bb38afc7cefaf47df718fffcf42d250
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842432"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="87e40-102">IManagedObject::GetSerializedBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="87e40-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="87e40-103">이 관리 되는 개체의 문자열 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="87e40-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87e40-104">구문</span><span class="sxs-lookup"><span data-stu-id="87e40-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87e40-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="87e40-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="87e40-106">제한이 Serialize 된 개체에 해당 하는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="87e40-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87e40-107">설명</span><span class="sxs-lookup"><span data-stu-id="87e40-107">Remarks</span></span>  
 <span data-ttu-id="87e40-108">`GetSerializedBuffer`메서드는 클라이언트에 마샬링될 수 있도록 개체를 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e40-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87e40-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87e40-109">Requirements</span></span>  
 <span data-ttu-id="87e40-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87e40-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87e40-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="87e40-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87e40-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87e40-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87e40-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87e40-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87e40-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87e40-114">See also</span></span>

- [<span data-ttu-id="87e40-115">IManagedObject 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87e40-115">IManagedObject Interface</span></span>](imanagedobject-interface.md)
