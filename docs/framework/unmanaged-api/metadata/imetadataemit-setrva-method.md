---
description: '자세히 알아보기: IMetaDataEmit:: SetRVA 메서드'
title: IMetaDataEmit::SetRVA 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
ms.openlocfilehash: 52294250df2b7a677bb4ecb09ea0a97baca595a5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771784"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="5cece-103">IMetaDataEmit::SetRVA 메서드</span><span class="sxs-lookup"><span data-stu-id="5cece-103">IMetaDataEmit::SetRVA Method</span></span>

<span data-ttu-id="5cece-104">지정 된 메서드의 상대 가상 주소를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cece-104">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cece-105">구문</span><span class="sxs-lookup"><span data-stu-id="5cece-105">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,
    [in]  ULONG        ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cece-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5cece-106">Parameters</span></span>  

 `md`  
 <span data-ttu-id="5cece-107">진행 대상 메서드 또는 메서드 구현에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5cece-107">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="5cece-108">진행 코드 또는 데이터 영역의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="5cece-108">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cece-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5cece-109">Requirements</span></span>  

 <span data-ttu-id="5cece-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5cece-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cece-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="5cece-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5cece-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cece-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5cece-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cece-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cece-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5cece-114">See also</span></span>

- [<span data-ttu-id="5cece-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5cece-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5cece-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5cece-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
