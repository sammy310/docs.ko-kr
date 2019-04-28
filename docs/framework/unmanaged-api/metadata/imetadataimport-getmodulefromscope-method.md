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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f40e6bfdbebdadc41da52564348c6070c18372c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777691"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="eb92a-102">IMetaDataImport::GetModuleFromScope 메서드</span><span class="sxs-lookup"><span data-stu-id="eb92a-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="eb92a-103">현재 메타 데이터 범위에서 참조 되는 모듈에 대 한 메타 데이터를 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eb92a-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb92a-104">구문</span><span class="sxs-lookup"><span data-stu-id="eb92a-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb92a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eb92a-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="eb92a-106">[out] 현재 메타 데이터 범위에서 참조 되는 모듈을 나타내는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eb92a-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb92a-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eb92a-107">Requirements</span></span>  
 <span data-ttu-id="eb92a-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="eb92a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb92a-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eb92a-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eb92a-110">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="eb92a-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eb92a-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb92a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb92a-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="eb92a-112">See also</span></span>

- [<span data-ttu-id="eb92a-113">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eb92a-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="eb92a-114">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eb92a-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
