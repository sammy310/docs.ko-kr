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
ms.openlocfilehash: 34b7cebfa063a3ad077b74a753fd37ba67ff53a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175319"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="0d0f8-102">IMetaDataImport::GetTypeSpecFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="0d0f8-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>
<span data-ttu-id="0d0f8-103">지정한 토큰이 나타내는 형식 사양의 이진 메타데이터 서명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0d0f8-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d0f8-104">구문</span><span class="sxs-lookup"><span data-stu-id="0d0f8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeSpecFromToken (
   [in]  mdTypeSpec            typespec,
   [out] PCCOR_SIGNATURE       *ppvSig,
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d0f8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0d0f8-105">Parameters</span></span>  
 `typespec`  
 <span data-ttu-id="0d0f8-106">【인】 요청된 메타데이터 서명과 연결된 TypeSpec 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0d0f8-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="0d0f8-107">【아웃】 이진 메타데이터 시그니처에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0d0f8-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="0d0f8-108">【아웃】 메타데이터 시그니처의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="0d0f8-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d0f8-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="0d0f8-109">Return Value</span></span>  
 <span data-ttu-id="0d0f8-110">성공 또는 실패를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="0d0f8-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="0d0f8-111">FAILED 매크로로 오류를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d0f8-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d0f8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d0f8-112">Requirements</span></span>  
 <span data-ttu-id="0d0f8-113">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d0f8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d0f8-114">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="0d0f8-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d0f8-115">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0d0f8-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0d0f8-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d0f8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d0f8-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d0f8-117">See also</span></span>

- [<span data-ttu-id="0d0f8-118">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d0f8-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0d0f8-119">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d0f8-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
