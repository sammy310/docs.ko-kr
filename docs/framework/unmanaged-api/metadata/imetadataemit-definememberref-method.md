---
title: IMetaDataEmit::DefineMemberRef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
ms.openlocfilehash: e371330336002c673f2c54d882e70dbed41b743c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175839"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="cc125-102">IMetaDataEmit::DefineMemberRef 메서드</span><span class="sxs-lookup"><span data-stu-id="cc125-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="cc125-103">현재 범위 외부의 모듈 멤버에 대한 참조를 정의하고 해당 참조 정의에 대한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc125-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc125-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc125-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc125-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc125-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="cc125-106">【인】 멤버가 전역이 아닌 경우 대상 멤버의 클래스 또는 인터페이스에 대한 토큰입니다. 멤버가 전역인 경우 `mdModuleRef` 해당 다른 파일에 대한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="cc125-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="cc125-107">【인】 대상 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cc125-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="cc125-108">【인】 대상 멤버의 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="cc125-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="cc125-109">【인】 의 바이트 `pvSigBlob`수입니다.</span><span class="sxs-lookup"><span data-stu-id="cc125-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="cc125-110">【아웃】 할당된 토큰입니다. `mdMemberRef`</span><span class="sxs-lookup"><span data-stu-id="cc125-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc125-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc125-111">Requirements</span></span>  
 <span data-ttu-id="cc125-112">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc125-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc125-113">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="cc125-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cc125-114">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="cc125-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc125-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc125-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc125-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc125-116">See also</span></span>

- [<span data-ttu-id="cc125-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc125-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="cc125-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc125-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
