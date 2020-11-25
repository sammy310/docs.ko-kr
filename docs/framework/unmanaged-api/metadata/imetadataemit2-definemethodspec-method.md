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
ms.openlocfilehash: 817b3a18b047bfca1f3a7c7099920a12e6253f58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712835"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="798f4-102">IMetaDataEmit2::DefineMethodSpec 메서드</span><span class="sxs-lookup"><span data-stu-id="798f4-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>

<span data-ttu-id="798f4-103">메서드의 제네릭 인스턴스를 만들고 해당 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="798f4-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="798f4-104">구문</span><span class="sxs-lookup"><span data-stu-id="798f4-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="798f4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="798f4-105">Parameters</span></span>  

 `tkParent`  
 <span data-ttu-id="798f4-106">진행 제네릭 인스턴스를 만들 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="798f4-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="798f4-107">토큰은 또는 형식 이어야 합니다 `mdMethodDef` `mdMemberRef` .</span><span class="sxs-lookup"><span data-stu-id="798f4-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="798f4-108">진행 메서드의 이진 COM + 시그니처에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="798f4-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="798f4-109">진행 의 크기 (바이트)입니다 `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="798f4-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="798f4-110">제한이 메서드의 메타 데이터 서명 정의에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="798f4-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="798f4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="798f4-111">Requirements</span></span>  

 <span data-ttu-id="798f4-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="798f4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="798f4-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="798f4-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="798f4-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="798f4-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="798f4-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="798f4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="798f4-116">참조</span><span class="sxs-lookup"><span data-stu-id="798f4-116">See also</span></span>

- [<span data-ttu-id="798f4-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="798f4-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="798f4-118">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="798f4-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
