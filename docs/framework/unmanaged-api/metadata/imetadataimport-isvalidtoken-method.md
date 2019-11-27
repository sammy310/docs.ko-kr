---
title: IMetaDataImport::IsValidToken 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsValidToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type:
- apiref
ms.openlocfilehash: edf24de8ae38aab97e41a53cc86ae5aa6c592c50
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434696"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="9bb8a-102">IMetaDataImport::IsValidToken 메서드</span><span class="sxs-lookup"><span data-stu-id="9bb8a-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="9bb8a-103">지정한 토큰이 코드 개체에 대한 유효한 참조를 포함하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bb8a-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bb8a-104">구문</span><span class="sxs-lookup"><span data-stu-id="9bb8a-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bb8a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9bb8a-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="9bb8a-106">진행 참조 유효성 검사에 사용할 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb8a-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9bb8a-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="9bb8a-107">Return Value</span></span>  
 <span data-ttu-id="9bb8a-108">`tk` 현재 범위 내의 유효한 메타 데이터 토큰이 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bb8a-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="9bb8a-109">그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb8a-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bb8a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9bb8a-110">Requirements</span></span>  
 <span data-ttu-id="9bb8a-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bb8a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bb8a-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="9bb8a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9bb8a-113">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bb8a-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9bb8a-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bb8a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bb8a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bb8a-115">See also</span></span>

- [<span data-ttu-id="9bb8a-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9bb8a-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9bb8a-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9bb8a-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
