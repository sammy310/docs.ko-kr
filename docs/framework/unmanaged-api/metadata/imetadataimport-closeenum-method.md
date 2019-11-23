---
title: IMetaDataImport::CloseEnum 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CloseEnum
helpviewer_keywords:
- IMetaDataImport::CloseEnum method [.NET Framework metadata]
- CloseEnum method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 727819d5-1dab-4ebb-ac25-950b4111dc72
topic_type:
- apiref
ms.openlocfilehash: 4347a4da3e58a20c98e217de3a71c448e244eb29
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440112"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="9f56d-102">IMetaDataImport::CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="9f56d-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="9f56d-103">Closes the enumerator that is identified by the specified handle.</span><span class="sxs-lookup"><span data-stu-id="9f56d-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f56d-104">구문</span><span class="sxs-lookup"><span data-stu-id="9f56d-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f56d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9f56d-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="9f56d-106">[in] The handle for the enumerator to close.</span><span class="sxs-lookup"><span data-stu-id="9f56d-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f56d-107">주의</span><span class="sxs-lookup"><span data-stu-id="9f56d-107">Remarks</span></span>  
 <span data-ttu-id="9f56d-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="9f56d-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f56d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9f56d-109">Requirements</span></span>  
 <span data-ttu-id="9f56d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f56d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f56d-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9f56d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9f56d-112">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9f56d-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9f56d-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f56d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f56d-114">참조</span><span class="sxs-lookup"><span data-stu-id="9f56d-114">See also</span></span>

- [<span data-ttu-id="9f56d-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9f56d-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9f56d-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9f56d-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
