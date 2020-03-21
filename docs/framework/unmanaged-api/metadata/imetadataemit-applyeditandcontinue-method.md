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
ms.openlocfilehash: f876187624d066b9e672fbf44a984d6d02a54c43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175878"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="37df9-102">IMetaDataEmit::ApplyEditAndContinue 메서드</span><span class="sxs-lookup"><span data-stu-id="37df9-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="37df9-103">지정된 메타데이터에 변경된 내용을 사용 하 고 현재 어셈블리 범위를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="37df9-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37df9-104">구문</span><span class="sxs-lookup"><span data-stu-id="37df9-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyEditAndContinue (
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37df9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37df9-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="37df9-106">\[휴대용\] 실행 파일(PE) 파일의 델타 메타데이터를 나타내는 [IUnknown](/cpp/atl/iunknown) 개체에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="37df9-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="37df9-107">델타 메타데이터는 모듈의 실제 메타데이터의 복사본에 대한 변경 내용을 포함하는 메타데이터의 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="37df9-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37df9-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37df9-108">Requirements</span></span>  
 <span data-ttu-id="37df9-109">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37df9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37df9-110">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="37df9-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="37df9-111">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="37df9-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37df9-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37df9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37df9-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37df9-113">See also</span></span>

- [<span data-ttu-id="37df9-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37df9-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="37df9-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37df9-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
