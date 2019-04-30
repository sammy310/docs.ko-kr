---
title: IMetaDataEmit2::GetDeltaSaveSize 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69897a7b646eb9f58e6b38588e302287b4241779
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043682"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="c1f2e-102">IMetaDataEmit2::GetDeltaSaveSize 메서드</span><span class="sxs-lookup"><span data-stu-id="c1f2e-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>
<span data-ttu-id="c1f2e-103">편집 하며 계속 하기는 현재 세션에서 발생 하는 메타 데이터 크기의 변화를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c1f2e-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1f2e-104">구문</span><span class="sxs-lookup"><span data-stu-id="c1f2e-104">Syntax</span></span>  
  
```  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1f2e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c1f2e-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="c1f2e-106">[in] 중 하나는 [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) 필요한 전체 자릿수 수준을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f2e-106">[in] One of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="c1f2e-107">.NET Framework 버전 2.0에서이 매개 변수는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f2e-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="c1f2e-108">[out] 메타 데이터의 크기를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f2e-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1f2e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1f2e-109">Requirements</span></span>  
 <span data-ttu-id="c1f2e-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1f2e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1f2e-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c1f2e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1f2e-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="c1f2e-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c1f2e-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1f2e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1f2e-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="c1f2e-114">See also</span></span>

- [<span data-ttu-id="c1f2e-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1f2e-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="c1f2e-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1f2e-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
