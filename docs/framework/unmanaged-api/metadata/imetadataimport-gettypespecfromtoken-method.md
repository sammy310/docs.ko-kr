---
title: IMetaDataImport::GetTypeSpecFromToken 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeSpecFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeSpecFromToken
helpviewer_keywords:
- GetTypeSpecFromToken method [.NET Framework metadata]
- IMetaDataImport::GetTypeSpecFromToken method [.NET Framework metadata]
ms.assetid: ee518bda-3296-482e-a7b7-e9d51dd1a181
topic_type:
- apiref
ms.openlocfilehash: 62495aa4280bb1799af09fea2e550ae6107e09e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729150"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="7d25f-102">IMetaDataImport::GetTypeSpecFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="7d25f-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>

<span data-ttu-id="7d25f-103">지정한 토큰이 나타내는 형식 사양의 이진 메타데이터 서명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d25f-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d25f-104">구문</span><span class="sxs-lookup"><span data-stu-id="7d25f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeSpecFromToken (
   [in]  mdTypeSpec            typespec,
   [out] PCCOR_SIGNATURE       *ppvSig,
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d25f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d25f-105">Parameters</span></span>  

 `typespec`  
 <span data-ttu-id="7d25f-106">진행 요청 된 메타 데이터 시그니처와 연결 된 TypeSpec 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7d25f-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="7d25f-107">제한이 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7d25f-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="7d25f-108">제한이 메타 데이터 시그니처의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="7d25f-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d25f-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="7d25f-109">Return Value</span></span>  

 <span data-ttu-id="7d25f-110">성공 또는 실패를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="7d25f-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="7d25f-111">실패 한 매크로를 사용 하 여 오류를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d25f-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d25f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d25f-112">Requirements</span></span>  

 <span data-ttu-id="7d25f-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d25f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d25f-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="7d25f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d25f-115">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d25f-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7d25f-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d25f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d25f-117">참조</span><span class="sxs-lookup"><span data-stu-id="7d25f-117">See also</span></span>

- [<span data-ttu-id="7d25f-118">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d25f-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="7d25f-119">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d25f-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
