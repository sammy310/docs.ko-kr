---
description: '자세히 알아보기: IMapToken:: Map 메서드'
title: IMapToken::Map 메서드
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
ms.openlocfilehash: da78f22e944a0e4ec25adcd7cdf97b69131a6612
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706736"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="388b0-103">IMapToken::Map 메서드</span><span class="sxs-lookup"><span data-stu-id="388b0-103">IMapToken::Map Method</span></span>

<span data-ttu-id="388b0-104">메타 데이터 시그니처를 사용 하 여 어셈블리 간의 관계를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="388b0-104">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="388b0-105">구문</span><span class="sxs-lookup"><span data-stu-id="388b0-105">Syntax</span></span>  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="388b0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="388b0-106">Parameters</span></span>  

 `tkImp`  
 <span data-ttu-id="388b0-107">진행 가져온 코드 개체를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="388b0-107">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="388b0-108">진행 내보낸 코드 개체를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="388b0-108">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="388b0-109">설명</span><span class="sxs-lookup"><span data-stu-id="388b0-109">Remarks</span></span>  

 <span data-ttu-id="388b0-110">병합 하는 동안 토큰 다시 맵이 발생 하면 원래 토큰은 가져온 (원본) 메타 데이터 범위에서 범위가 지정 되 고 새 토큰은 내보낸 (대상) 메타 데이터 범위에서 범위가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="388b0-110">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="388b0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="388b0-111">Requirements</span></span>  

 <span data-ttu-id="388b0-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="388b0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="388b0-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="388b0-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="388b0-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="388b0-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="388b0-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="388b0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="388b0-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="388b0-116">See also</span></span>

- [<span data-ttu-id="388b0-117">IMapToken 인터페이스</span><span class="sxs-lookup"><span data-stu-id="388b0-117">IMapToken Interface</span></span>](imaptoken-interface.md)
