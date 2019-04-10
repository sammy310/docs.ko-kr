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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a85dc586b0c08fabdd34c018e82314c9003eeded
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171017"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="b4cf5-102">IMapToken::Map 메서드</span><span class="sxs-lookup"><span data-stu-id="b4cf5-102">IMapToken::Map Method</span></span>
<span data-ttu-id="b4cf5-103">메타 데이터 서명을 사용 하 여 어셈블리 간에 관계를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b4cf5-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4cf5-104">구문</span><span class="sxs-lookup"><span data-stu-id="b4cf5-104">Syntax</span></span>  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4cf5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4cf5-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="b4cf5-106">[in] 가져온된 코드 개체를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b4cf5-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="b4cf5-107">[in] 내보낸된 코드가 개체를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b4cf5-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4cf5-108">설명</span><span class="sxs-lookup"><span data-stu-id="b4cf5-108">Remarks</span></span>  
 <span data-ttu-id="b4cf5-109">토큰 다시 매핑하는 경우 병합 하는 동안 가져온된 (원본) 메타 데이터 범위에서 사용 하는 원래 토큰에서 범위를 지정 하 고 내보낸된 (대상) 메타 데이터 범위에서 사용 하는 새 토큰에서 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4cf5-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4cf5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4cf5-110">Requirements</span></span>  
 <span data-ttu-id="b4cf5-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4cf5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4cf5-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b4cf5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4cf5-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b4cf5-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="b4cf5-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="b4cf5-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b4cf5-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="b4cf5-115">See also</span></span>

- [<span data-ttu-id="b4cf5-116">IMapToken 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4cf5-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
