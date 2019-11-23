---
title: IMetaDataImport::CountEnum 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CountEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CountEnum
helpviewer_keywords:
- CountEnum method [.NET Framework metadata]
- IMetaDataImport::CountEnum method [.NET Framework metadata]
ms.assetid: d1de53ad-9435-4b5f-9df7-07f21210e5b5
topic_type:
- apiref
ms.openlocfilehash: 0c78ce8192d6456dd1b1be990d87b9209b028e09
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440364"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="2e29b-102">IMetaDataImport::CountEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="2e29b-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="2e29b-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span><span class="sxs-lookup"><span data-stu-id="2e29b-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e29b-104">구문</span><span class="sxs-lookup"><span data-stu-id="2e29b-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,   
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e29b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2e29b-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="2e29b-106">[in] The handle for the enumerator.</span><span class="sxs-lookup"><span data-stu-id="2e29b-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="2e29b-107">[out] The number of elements enumerated.</span><span class="sxs-lookup"><span data-stu-id="2e29b-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e29b-108">주의</span><span class="sxs-lookup"><span data-stu-id="2e29b-108">Remarks</span></span>  
 <span data-ttu-id="2e29b-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="2e29b-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e29b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e29b-110">Requirements</span></span>  
 <span data-ttu-id="2e29b-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e29b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e29b-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2e29b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2e29b-113">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2e29b-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2e29b-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e29b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e29b-115">참조</span><span class="sxs-lookup"><span data-stu-id="2e29b-115">See also</span></span>

- [<span data-ttu-id="2e29b-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e29b-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2e29b-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e29b-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
