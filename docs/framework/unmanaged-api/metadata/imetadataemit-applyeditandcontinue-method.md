---
title: IMetaDataEmit::ApplyEditAndContinue 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.ApplyEditAndContinue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::ApplyEditAndContinue
helpviewer_keywords:
- ApplyEditAndContinue method [.NET Framework metadata]
- IMetaDataEmit::ApplyEditAndContinue method [.NET Framework metadata]
ms.assetid: 35991289-f389-495d-8caa-a6384fb1d557
topic_type:
- apiref
ms.openlocfilehash: 7ce9ac95c7183a7d47c367914d80f77c57dde0d7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005767"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="c120b-102">IMetaDataEmit::ApplyEditAndContinue 메서드</span><span class="sxs-lookup"><span data-stu-id="c120b-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="c120b-103">지정 된 메타 데이터에서 변경한 내용으로 현재 어셈블리 범위를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="c120b-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c120b-104">구문</span><span class="sxs-lookup"><span data-stu-id="c120b-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyEditAndContinue (
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c120b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c120b-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="c120b-106">\[\]pe (이식 가능한 실행 파일) 파일의 델타 메타 데이터를 나타내는 [IUnknown](/cpp/atl/iunknown) 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c120b-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="c120b-107">델타 메타 데이터는 모듈의 실제 메타 데이터 복사본에 적용 된 변경 내용을 포함 하는 메타 데이터의 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="c120b-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c120b-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c120b-108">Requirements</span></span>  
 <span data-ttu-id="c120b-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c120b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c120b-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="c120b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c120b-111">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c120b-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c120b-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c120b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c120b-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c120b-113">See also</span></span>

- [<span data-ttu-id="c120b-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c120b-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="c120b-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c120b-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
