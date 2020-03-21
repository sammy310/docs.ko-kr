---
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
ms.openlocfilehash: 428b022ed560648f59798154d5987d382938c280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176073"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="b6dd7-102">IMapToken::Map 메서드</span><span class="sxs-lookup"><span data-stu-id="b6dd7-102">IMapToken::Map Method</span></span>
<span data-ttu-id="b6dd7-103">메타데이터 서명을 사용하여 어셈블리 간의 관계를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b6dd7-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6dd7-104">구문</span><span class="sxs-lookup"><span data-stu-id="b6dd7-104">Syntax</span></span>  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6dd7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b6dd7-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="b6dd7-106">【인】 가져온 코드 개체를 나타내는 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b6dd7-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="b6dd7-107">【인】 내보낸 코드 개체를 나타내는 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b6dd7-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6dd7-108">설명</span><span class="sxs-lookup"><span data-stu-id="b6dd7-108">Remarks</span></span>  
 <span data-ttu-id="b6dd7-109">병합 중에 토큰 다시 맵이 발생하면 원래 토큰은 가져온(원본) 메타데이터 범위에서 범위가 지정되고 새 토큰은 내보낸(대상) 메타데이터 범위에서 범위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6dd7-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6dd7-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6dd7-110">Requirements</span></span>  
 <span data-ttu-id="b6dd7-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6dd7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6dd7-112">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="b6dd7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6dd7-113">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b6dd7-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b6dd7-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6dd7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6dd7-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6dd7-115">See also</span></span>

- [<span data-ttu-id="b6dd7-116">IMapToken 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6dd7-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
