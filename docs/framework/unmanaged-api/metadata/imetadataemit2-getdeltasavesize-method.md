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
ms.openlocfilehash: 36021333c1efb61e23c16782d8ad721de62c2643
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674341"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="e3060-102">IMetaDataEmit2::GetDeltaSaveSize 메서드</span><span class="sxs-lookup"><span data-stu-id="e3060-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>

<span data-ttu-id="e3060-103">현재 편집 하며 계속 하기 세션에서 발생 하는 메타 데이터 크기 변경 내용을 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e3060-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3060-104">구문</span><span class="sxs-lookup"><span data-stu-id="e3060-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3060-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e3060-105">Parameters</span></span>  

 `fSave`  
 <span data-ttu-id="e3060-106">진행 원하는 정밀도 수준을 나타내는 [CorSaveSize](corsavesize-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="e3060-106">[in] One of the [CorSaveSize](corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="e3060-107">.NET Framework 버전 2.0의 경우이 매개 변수는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3060-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="e3060-108">제한이 메타 데이터의 크기 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="e3060-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3060-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e3060-109">Requirements</span></span>  

 <span data-ttu-id="e3060-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3060-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3060-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="e3060-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e3060-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3060-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e3060-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3060-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3060-114">참조</span><span class="sxs-lookup"><span data-stu-id="e3060-114">See also</span></span>

- [<span data-ttu-id="e3060-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e3060-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="e3060-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e3060-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
