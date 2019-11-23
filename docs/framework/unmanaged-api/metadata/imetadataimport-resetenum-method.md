---
title: IMetaDataImport::ResetEnum 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResetEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type:
- apiref
ms.openlocfilehash: 3f965ab215ff861c6df61de82dcbbea6b389c8da
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426774"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="2aaf1-102">IMetaDataImport::ResetEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="2aaf1-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="2aaf1-103">지정한 열거자를 지정한 위치로 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2aaf1-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aaf1-104">구문</span><span class="sxs-lookup"><span data-stu-id="2aaf1-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2aaf1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2aaf1-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="2aaf1-106">[in] The enumerator to reset.</span><span class="sxs-lookup"><span data-stu-id="2aaf1-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="2aaf1-107">[in] The new position at which to place the enumerator.</span><span class="sxs-lookup"><span data-stu-id="2aaf1-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aaf1-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2aaf1-108">Requirements</span></span>  
 <span data-ttu-id="2aaf1-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2aaf1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2aaf1-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2aaf1-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2aaf1-111">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2aaf1-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2aaf1-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2aaf1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aaf1-113">참조</span><span class="sxs-lookup"><span data-stu-id="2aaf1-113">See also</span></span>

- [<span data-ttu-id="2aaf1-114">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2aaf1-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2aaf1-115">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2aaf1-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
