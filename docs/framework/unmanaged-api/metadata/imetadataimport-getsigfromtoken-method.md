---
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
ms.openlocfilehash: d795f90c458b7fcf1a191b2763ac5f5bb55fb438
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490903"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="d2203-102">IMetaDataImport::GetSigFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="d2203-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="d2203-103">지정한 토큰과 연결된 이진 메타데이터 서명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d2203-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2203-104">구문</span><span class="sxs-lookup"><span data-stu-id="d2203-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSigFromToken (
   [in]   mdSignature        mdSig,
   [out]  PCCOR_SIGNATURE    *ppvSig,
   [out]  ULONG              *pcbSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2203-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d2203-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="d2203-106">진행 이진 메타 데이터 서명을 반환할 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d2203-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="d2203-107">제한이 반환 된 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d2203-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="d2203-108">제한이 이진 메타 데이터 시그니처의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d2203-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2203-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2203-109">Requirements</span></span>  
 <span data-ttu-id="d2203-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2203-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2203-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d2203-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2203-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2203-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d2203-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2203-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2203-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2203-114">See also</span></span>

- [<span data-ttu-id="d2203-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2203-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="d2203-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2203-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
