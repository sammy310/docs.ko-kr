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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5543313a8d7a5589e115d609923aa0e75d3e275
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484968"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="921f6-102">IMetaDataImport::ResetEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="921f6-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="921f6-103">지정한 열거자를 지정한 위치로 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="921f6-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="921f6-104">구문</span><span class="sxs-lookup"><span data-stu-id="921f6-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="921f6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="921f6-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="921f6-106">[in] 다시 설정 하는 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="921f6-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="921f6-107">[in] 열거자를 배치할 새 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="921f6-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="921f6-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="921f6-108">Requirements</span></span>  
 <span data-ttu-id="921f6-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="921f6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="921f6-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="921f6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="921f6-111">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="921f6-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="921f6-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="921f6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="921f6-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="921f6-113">See also</span></span>
- [<span data-ttu-id="921f6-114">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="921f6-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="921f6-115">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="921f6-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
