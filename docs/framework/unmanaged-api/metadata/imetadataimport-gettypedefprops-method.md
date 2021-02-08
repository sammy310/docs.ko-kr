---
description: '자세히 알아보기: IMetaDataImport:: GetTypeDefProps 메서드'
title: IMetaDataImport::GetTypeDefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
ms.openlocfilehash: da5c6117f636098ed0cfeddc541979d235729d63
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799280"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="58e00-103">IMetaDataImport::GetTypeDefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="58e00-103">IMetaDataImport::GetTypeDefProps Method</span></span>

<span data-ttu-id="58e00-104">지정 된 TypeDef 토큰이 나타내는에 대 한 메타 데이터 정보를 반환 합니다 <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="58e00-104">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58e00-105">구문</span><span class="sxs-lookup"><span data-stu-id="58e00-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58e00-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="58e00-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="58e00-107">진행 메타 데이터를 반환할 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="58e00-107">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="58e00-108">제한이 형식 이름을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="58e00-108">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="58e00-109">진행 의 와이드 문자 크기입니다 `szTypeDef` .</span><span class="sxs-lookup"><span data-stu-id="58e00-109">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="58e00-110">제한이 에서 반환 되는 와이드 문자 수입니다 `szTypeDef` .</span><span class="sxs-lookup"><span data-stu-id="58e00-110">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="58e00-111">제한이 형식 정의를 수정 하는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="58e00-111">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="58e00-112">이 값은 [Cortypeattr](cortypeattr-enumeration.md) 열거형의 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="58e00-112">This value is a bitmask from the [CorTypeAttr](cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="58e00-113">제한이 요청 된 형식의 기본 형식을 나타내는 TypeDef 또는 TypeRef 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="58e00-113">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58e00-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58e00-114">Requirements</span></span>  

 <span data-ttu-id="58e00-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58e00-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58e00-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="58e00-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58e00-117">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58e00-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58e00-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58e00-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58e00-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58e00-119">See also</span></span>

- [<span data-ttu-id="58e00-120">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58e00-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="58e00-121">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58e00-121">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
