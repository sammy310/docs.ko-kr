---
description: IMetaDataEmit2::D efineMethodSpec 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 4b5283375ba194a86a83b142b3b2bdc06bfd35da
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745738"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="02a86-103">IMetaDataEmit2::DefineMethodSpec 메서드</span><span class="sxs-lookup"><span data-stu-id="02a86-103">IMetaDataEmit2::DefineMethodSpec Method</span></span>

<span data-ttu-id="02a86-104">메서드의 제네릭 인스턴스를 만들고 해당 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="02a86-104">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02a86-105">구문</span><span class="sxs-lookup"><span data-stu-id="02a86-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02a86-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02a86-106">Parameters</span></span>  

 `tkParent`  
 <span data-ttu-id="02a86-107">진행 제네릭 인스턴스를 만들 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="02a86-107">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="02a86-108">토큰은 또는 형식 이어야 합니다 `mdMethodDef` `mdMemberRef` .</span><span class="sxs-lookup"><span data-stu-id="02a86-108">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="02a86-109">진행 메서드의 이진 COM + 시그니처에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="02a86-109">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="02a86-110">진행 의 크기 (바이트)입니다 `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="02a86-110">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="02a86-111">제한이 메서드의 메타 데이터 서명 정의에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="02a86-111">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02a86-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02a86-112">Requirements</span></span>  

 <span data-ttu-id="02a86-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02a86-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02a86-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="02a86-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="02a86-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02a86-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="02a86-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02a86-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a86-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02a86-117">See also</span></span>

- [<span data-ttu-id="02a86-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02a86-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="02a86-119">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02a86-119">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
