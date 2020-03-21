---
title: IMetaDataEmit::DeletePinvokeMap 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeletePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type:
- apiref
ms.openlocfilehash: 45f40dcd419e8e2fdf8a3349ccc9461854ad9aaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175735"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="8556f-102">IMetaDataEmit::DeletePinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="8556f-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="8556f-103">지정된 토큰에서 참조하는 개체에 대한 PInvoke 매핑 메타데이터를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="8556f-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8556f-104">구문</span><span class="sxs-lookup"><span data-stu-id="8556f-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8556f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8556f-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="8556f-106">【인】 PInvoke 매핑 메타데이터를 삭제할 개체를 나타내는 `mdFieldDef` 또는 `mdMethodDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8556f-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8556f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8556f-107">Requirements</span></span>  
 <span data-ttu-id="8556f-108">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8556f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8556f-109">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="8556f-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8556f-110">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="8556f-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8556f-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8556f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8556f-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8556f-112">See also</span></span>

- [<span data-ttu-id="8556f-113">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8556f-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8556f-114">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8556f-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
