---
title: IMetaDataEmit2::DefineMethodSpec 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineMethodSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type:
- apiref
ms.openlocfilehash: a5d9342b8bfe650106ccf9daf2a91dfbcd575446
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175541"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="5f352-102">IMetaDataEmit2::DefineMethodSpec 메서드</span><span class="sxs-lookup"><span data-stu-id="5f352-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="5f352-103">메서드의 제네릭 인스턴스를 만들고 정의에 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5f352-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f352-104">구문</span><span class="sxs-lookup"><span data-stu-id="5f352-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f352-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5f352-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="5f352-106">【인】 제네릭 인스턴스를 만드는 메서드에 대한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5f352-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="5f352-107">토큰은 형식 `mdMethodDef` 또는 `mdMemberRef`에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f352-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="5f352-108">【인】 메서드의 이진 COM+ 시그니처에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5f352-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="5f352-109">【인】 의 크기(바이트)입니다. `pvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="5f352-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="5f352-110">【아웃】 메서드의 메타데이터 서명 정의에 대한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5f352-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f352-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f352-111">Requirements</span></span>  
 <span data-ttu-id="5f352-112">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f352-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f352-113">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="5f352-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f352-114">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="5f352-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f352-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f352-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f352-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f352-116">See also</span></span>

- [<span data-ttu-id="5f352-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f352-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="5f352-118">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f352-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
