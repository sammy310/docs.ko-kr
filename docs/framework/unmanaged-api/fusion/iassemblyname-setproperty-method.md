---
title: IAssemblyName::SetProperty 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.SetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type:
- apiref
ms.openlocfilehash: 04b3e73e2166efb2ec0821d21da3da4c53b0ca4b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688655"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="326c3-102">IAssemblyName::SetProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="326c3-102">IAssemblyName::SetProperty Method</span></span>

<span data-ttu-id="326c3-103">지정 된 속성 식별자가 참조 하는 속성의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="326c3-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="326c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="326c3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="326c3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="326c3-105">Parameters</span></span>  

 `PropertyId`  
 <span data-ttu-id="326c3-106">진행 값을 설정할 속성의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="326c3-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="326c3-107">진행 에서 참조 하는 속성을 설정 하는 데 사용할 값입니다 `PropertyId` .</span><span class="sxs-lookup"><span data-stu-id="326c3-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="326c3-108">진행 의 크기 (바이트)입니다 `pvProperty` .</span><span class="sxs-lookup"><span data-stu-id="326c3-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="326c3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="326c3-109">Requirements</span></span>  

 <span data-ttu-id="326c3-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="326c3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="326c3-111">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="326c3-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="326c3-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="326c3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="326c3-113">참조</span><span class="sxs-lookup"><span data-stu-id="326c3-113">See also</span></span>

- [<span data-ttu-id="326c3-114">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="326c3-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
