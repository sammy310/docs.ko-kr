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
ms.openlocfilehash: 143b11f0a99081b7d49bfbb68b635d92cf1e9ba3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163880"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="a84d7-102">IMetaDataImport::ResetEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="a84d7-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="a84d7-103">지정한 열거자를 지정한 위치로 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a84d7-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a84d7-104">구문</span><span class="sxs-lookup"><span data-stu-id="a84d7-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a84d7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a84d7-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="a84d7-106">[in] 다시 설정 하는 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="a84d7-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="a84d7-107">[in] 열거자를 배치할 새 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="a84d7-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a84d7-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a84d7-108">Requirements</span></span>  
 <span data-ttu-id="a84d7-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a84d7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a84d7-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a84d7-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a84d7-111">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a84d7-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="a84d7-112">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="a84d7-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a84d7-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="a84d7-113">See also</span></span>

- [<span data-ttu-id="a84d7-114">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a84d7-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a84d7-115">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a84d7-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
