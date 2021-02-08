---
description: '자세히 알아보기: IMetaDataImport:: GetSigFromToken 메서드'
title: IMetaDataImport::GetSigFromToken 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetSigFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetSigFromToken
helpviewer_keywords:
- IMetaDataImport::GetSigFromToken method [.NET Framework metadata]
- GetSigFromToken method [.NET Framework metadata]
ms.assetid: ab894dc4-f7b6-4afc-bfcb-582a4b7e53a2
topic_type:
- apiref
ms.openlocfilehash: 16b77fe5866319e24b33ec4ce9d2d56797f04514
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789140"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="ae703-103">IMetaDataImport::GetSigFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="ae703-103">IMetaDataImport::GetSigFromToken Method</span></span>

<span data-ttu-id="ae703-104">지정한 토큰과 연결된 이진 메타데이터 서명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae703-104">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae703-105">구문</span><span class="sxs-lookup"><span data-stu-id="ae703-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSigFromToken (
   [in]   mdSignature        mdSig,
   [out]  PCCOR_SIGNATURE    *ppvSig,
   [out]  ULONG              *pcbSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae703-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae703-106">Parameters</span></span>  

 `mdSig`  
 <span data-ttu-id="ae703-107">진행 이진 메타 데이터 서명을 반환할 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ae703-107">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="ae703-108">제한이 반환 된 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ae703-108">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="ae703-109">제한이 이진 메타 데이터 시그니처의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="ae703-109">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae703-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae703-110">Requirements</span></span>  

 <span data-ttu-id="ae703-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae703-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae703-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="ae703-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ae703-113">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae703-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ae703-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae703-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae703-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae703-115">See also</span></span>

- [<span data-ttu-id="ae703-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae703-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ae703-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae703-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
