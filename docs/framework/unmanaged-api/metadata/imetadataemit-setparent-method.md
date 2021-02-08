---
description: '자세히 알아보기: IMetaDataEmit:: SetParent 메서드'
title: IMetaDataEmit::SetParent 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
ms.openlocfilehash: 9025d4a37de85a0e657059f63ef781dc4377c036
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772005"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="afdba-103">IMetaDataEmit::SetParent 메서드</span><span class="sxs-lookup"><span data-stu-id="afdba-103">IMetaDataEmit::SetParent Method</span></span>

<span data-ttu-id="afdba-104">[IMetaDataEmit::D efinememberref](imetadataemit-definememberref-method.md)에 대 한 이전 호출로 정의 된 지정 된 멤버가 [IMetaDataEmit::D Efin def](imetadataemit-definetypedef-method.md)의 이전 호출에 정의 된 대로 지정 된 형식의 멤버 임을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="afdba-104">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afdba-105">구문</span><span class="sxs-lookup"><span data-stu-id="afdba-105">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afdba-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="afdba-106">Parameters</span></span>  

 `mr`  
 <span data-ttu-id="afdba-107">진행 `mdMemberRef` 새 부모를 받을 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="afdba-107">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="afdba-108">진행 `mdToken` 새 부모에 대 한입니다.</span><span class="sxs-lookup"><span data-stu-id="afdba-108">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afdba-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="afdba-109">Requirements</span></span>  

 <span data-ttu-id="afdba-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="afdba-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afdba-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="afdba-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="afdba-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="afdba-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="afdba-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afdba-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afdba-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="afdba-114">See also</span></span>

- [<span data-ttu-id="afdba-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="afdba-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="afdba-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="afdba-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
