---
title: IMetaDataImport::GetModuleFromScope 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type:
- apiref
ms.openlocfilehash: 026a952e14cda2ef4ebc32ca91006026e920e3c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437364"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="cb1fd-102">IMetaDataImport::GetModuleFromScope 메서드</span><span class="sxs-lookup"><span data-stu-id="cb1fd-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="cb1fd-103">Gets a metadata token for the module referenced in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="cb1fd-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb1fd-104">구문</span><span class="sxs-lookup"><span data-stu-id="cb1fd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb1fd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb1fd-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="cb1fd-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="cb1fd-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb1fd-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb1fd-107">Requirements</span></span>  
 <span data-ttu-id="cb1fd-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb1fd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb1fd-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cb1fd-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cb1fd-110">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cb1fd-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cb1fd-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb1fd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb1fd-112">참조</span><span class="sxs-lookup"><span data-stu-id="cb1fd-112">See also</span></span>

- [<span data-ttu-id="cb1fd-113">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb1fd-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="cb1fd-114">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb1fd-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
