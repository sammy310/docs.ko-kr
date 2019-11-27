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
ms.openlocfilehash: 219d3196e3b2125033a23623b7e77e31c6f1ff03
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440490"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="bbd4d-102">IMetaDataEmit2::GetDeltaSaveSize 메서드</span><span class="sxs-lookup"><span data-stu-id="bbd4d-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>
<span data-ttu-id="bbd4d-103">현재 편집 하며 계속 하기 세션에서 발생 하는 메타 데이터 크기 변경 내용을 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbd4d-104">구문</span><span class="sxs-lookup"><span data-stu-id="bbd4d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbd4d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bbd4d-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="bbd4d-106">진행 원하는 정밀도 수준을 나타내는 [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-106">[in] One of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="bbd4d-107">.NET Framework 버전 2.0의 경우이 매개 변수는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="bbd4d-108">제한이 메타 데이터의 크기 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbd4d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bbd4d-109">Requirements</span></span>  
 <span data-ttu-id="bbd4d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbd4d-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="bbd4d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bbd4d-112">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bbd4d-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbd4d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbd4d-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="bbd4d-114">See also</span></span>

- [<span data-ttu-id="bbd4d-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bbd4d-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="bbd4d-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bbd4d-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
