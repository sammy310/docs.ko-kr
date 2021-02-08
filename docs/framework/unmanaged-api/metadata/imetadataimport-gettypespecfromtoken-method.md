---
description: '자세히 알아보기: IMetaDataImport:: GetTypeSpecFromToken 메서드'
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
ms.openlocfilehash: b71f8f856da517b3e5046c20d787a555816fb728
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789114"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="8f6aa-103">IMetaDataImport::GetTypeSpecFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="8f6aa-103">IMetaDataImport::GetTypeSpecFromToken Method</span></span>

<span data-ttu-id="8f6aa-104">지정한 토큰이 나타내는 형식 사양의 이진 메타데이터 서명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f6aa-104">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f6aa-105">구문</span><span class="sxs-lookup"><span data-stu-id="8f6aa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeSpecFromToken (
   [in]  mdTypeSpec            typespec,
   [out] PCCOR_SIGNATURE       *ppvSig,
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f6aa-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f6aa-106">Parameters</span></span>  

 `typespec`  
 <span data-ttu-id="8f6aa-107">진행 요청 된 메타 데이터 시그니처와 연결 된 TypeSpec 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8f6aa-107">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="8f6aa-108">제한이 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8f6aa-108">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="8f6aa-109">제한이 메타 데이터 시그니처의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f6aa-109">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f6aa-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="8f6aa-110">Return Value</span></span>  

 <span data-ttu-id="8f6aa-111">성공 또는 실패를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="8f6aa-111">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="8f6aa-112">실패 한 매크로를 사용 하 여 오류를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f6aa-112">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f6aa-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f6aa-113">Requirements</span></span>  

 <span data-ttu-id="8f6aa-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f6aa-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f6aa-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8f6aa-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8f6aa-116">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f6aa-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8f6aa-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f6aa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f6aa-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f6aa-118">See also</span></span>

- [<span data-ttu-id="8f6aa-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f6aa-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="8f6aa-120">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f6aa-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
