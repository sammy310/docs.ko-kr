---
description: '자세히 알아보기: IMetaDataEmit:: SetMethodImplFlags 메서드'
title: IMetaDataEmit::SetMethodImplFlags 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
ms.openlocfilehash: ea7f3122a21c8651014e60de3629db87eeaf6260
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657837"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="8bf32-103">IMetaDataEmit::SetMethodImplFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="8bf32-103">IMetaDataEmit::SetMethodImplFlags Method</span></span>

<span data-ttu-id="8bf32-104">지정 된 토큰이 참조 하는 상속 된 메서드 구현의 메타 데이터 서명을 설정 하거나 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf32-104">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bf32-105">구문</span><span class="sxs-lookup"><span data-stu-id="8bf32-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (
    [in]  mdMethodDef   md,
    [in]  DWORD         dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bf32-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8bf32-106">Parameters</span></span>  

 `md`  
 <span data-ttu-id="8bf32-107">진행 변경할 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf32-107">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="8bf32-108">진행 메서드 구현 기능을 지정 하는 [Cormethodimpl](cormethodimpl-enumeration.md) 열거형 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf32-108">[in] A combination of the values of the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bf32-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bf32-109">Requirements</span></span>  

 <span data-ttu-id="8bf32-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bf32-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bf32-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8bf32-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8bf32-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bf32-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8bf32-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bf32-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bf32-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8bf32-114">See also</span></span>

- [<span data-ttu-id="8bf32-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bf32-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8bf32-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bf32-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
