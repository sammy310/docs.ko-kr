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
ms.openlocfilehash: 52c35b3bd726d4c83c6745bf99940faa44ea7338
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702852"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="3a852-102">IMetaDataImport::ResetEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="3a852-102">IMetaDataImport::ResetEnum Method</span></span>

<span data-ttu-id="3a852-103">지정한 열거자를 지정한 위치로 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a852-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a852-104">구문</span><span class="sxs-lookup"><span data-stu-id="3a852-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a852-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3a852-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="3a852-106">진행 다시 설정할 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="3a852-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="3a852-107">진행 열거자를 배치할 새 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="3a852-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a852-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a852-108">Requirements</span></span>  

 <span data-ttu-id="3a852-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a852-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a852-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="3a852-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a852-111">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a852-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a852-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a852-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a852-113">참조</span><span class="sxs-lookup"><span data-stu-id="3a852-113">See also</span></span>

- [<span data-ttu-id="3a852-114">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a852-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3a852-115">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a852-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
