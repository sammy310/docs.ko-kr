---
description: '자세히 알아보기: IMetaDataEmit2:: GetDeltaSaveSize 메서드'
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
ms.openlocfilehash: d7b5eae7f89a5465876083c5cc8021330d3c59de
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745764"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="b476a-103">IMetaDataEmit2::GetDeltaSaveSize 메서드</span><span class="sxs-lookup"><span data-stu-id="b476a-103">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>

<span data-ttu-id="b476a-104">현재 편집 하며 계속 하기 세션에서 발생 하는 메타 데이터 크기 변경 내용을 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b476a-104">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b476a-105">구문</span><span class="sxs-lookup"><span data-stu-id="b476a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b476a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b476a-106">Parameters</span></span>  

 `fSave`  
 <span data-ttu-id="b476a-107">진행 원하는 정밀도 수준을 나타내는 [CorSaveSize](corsavesize-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="b476a-107">[in] One of the [CorSaveSize](corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="b476a-108">.NET Framework 버전 2.0의 경우이 매개 변수는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b476a-108">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="b476a-109">제한이 메타 데이터의 크기 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="b476a-109">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b476a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b476a-110">Requirements</span></span>  

 <span data-ttu-id="b476a-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b476a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b476a-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="b476a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b476a-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b476a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b476a-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b476a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b476a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b476a-115">See also</span></span>

- [<span data-ttu-id="b476a-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b476a-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="b476a-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b476a-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
