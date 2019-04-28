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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2cc2a2c7991eb4d11873ebb6a2df92ccc45cde9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697227"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="64e37-102">IAssemblyName::SetProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="64e37-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="64e37-103">지정 된 속성 식별자가 참조 하는 속성의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e37-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64e37-104">구문</span><span class="sxs-lookup"><span data-stu-id="64e37-104">Syntax</span></span>  
  
```  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64e37-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="64e37-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="64e37-106">[in] 해당 값을 설정할 속성의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="64e37-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="64e37-107">[in] 참조 하는 속성을 설정 하는 값 `PropertyId`합니다.</span><span class="sxs-lookup"><span data-stu-id="64e37-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="64e37-108">[in] 크기 (바이트)의 `pvProperty`합니다.</span><span class="sxs-lookup"><span data-stu-id="64e37-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64e37-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="64e37-109">Requirements</span></span>  
 <span data-ttu-id="64e37-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="64e37-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64e37-111">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="64e37-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="64e37-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64e37-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64e37-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="64e37-113">See also</span></span>

- [<span data-ttu-id="64e37-114">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64e37-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
