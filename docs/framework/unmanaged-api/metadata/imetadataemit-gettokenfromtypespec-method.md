---
description: '자세히 알아보기: IMetaDataEmit:: GetTokenFromTypeSpec 메서드'
title: IMetaDataEmit::GetTokenFromTypeSpec 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
ms.openlocfilehash: 09f7133af9b9d912b03cdc1c93744ee260c69169
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728238"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="f3f71-103">IMetaDataEmit::GetTokenFromTypeSpec 메서드</span><span class="sxs-lookup"><span data-stu-id="f3f71-103">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>

<span data-ttu-id="f3f71-104">지정 된 메타 데이터 서명을 사용 하 여 형식에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f3f71-104">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3f71-105">구문</span><span class="sxs-lookup"><span data-stu-id="f3f71-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (
    [in]  PCCOR_SIGNATURE       pvSig,
    [in]  ULONG                 cbSig,
    [out] mdTypeSpec            *ptypespec
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3f71-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f3f71-106">Parameters</span></span>  

 `pvSig`  
 <span data-ttu-id="f3f71-107">진행 정의 되는 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="f3f71-107">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="f3f71-108">진행 의 바이트 수 `pvSig` 입니다.</span><span class="sxs-lookup"><span data-stu-id="f3f71-108">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="f3f71-109">제한이 `mdTypeSpec` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f3f71-109">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3f71-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f3f71-110">Requirements</span></span>  

 <span data-ttu-id="f3f71-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3f71-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3f71-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="f3f71-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f3f71-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3f71-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3f71-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3f71-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3f71-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3f71-115">See also</span></span>

- [<span data-ttu-id="f3f71-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3f71-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f3f71-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3f71-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
