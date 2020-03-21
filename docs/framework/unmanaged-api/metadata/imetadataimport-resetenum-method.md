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
ms.openlocfilehash: 3dd82588cf2dbf92fdda66fd7674c17ddc8b7306
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177185"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="5c415-102">IMetaDataImport::ResetEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="5c415-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="5c415-103">지정한 열거자를 지정한 위치로 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c415-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c415-104">구문</span><span class="sxs-lookup"><span data-stu-id="5c415-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c415-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5c415-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="5c415-106">【인】 열거자가 재설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c415-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="5c415-107">【인】 열거기를 배치할 새 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="5c415-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c415-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c415-108">Requirements</span></span>  
 <span data-ttu-id="5c415-109">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c415-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c415-110">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="5c415-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c415-111">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5c415-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c415-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c415-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c415-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c415-113">See also</span></span>

- [<span data-ttu-id="5c415-114">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c415-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5c415-115">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c415-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
