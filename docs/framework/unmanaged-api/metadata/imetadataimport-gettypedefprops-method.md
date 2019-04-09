---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a482c7a06efe888408206f2de569e0a8739b85b8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121513"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="79804-102">IMetaDataImport::GetTypeDefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="79804-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="79804-103">메타 데이터 정보를 반환 합니다 <xref:System.Type> 지정한 TypeDef 토큰이 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="79804-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79804-104">구문</span><span class="sxs-lookup"><span data-stu-id="79804-104">Syntax</span></span>  
  
```  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79804-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="79804-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="79804-106">[in] 에 대 한 메타 데이터를 반환할 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="79804-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="79804-107">[out] 형식 이름을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="79804-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="79804-108">[in] 와이드 문자에서 크기 `szTypeDef`합니다.</span><span class="sxs-lookup"><span data-stu-id="79804-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="79804-109">[out] 반환 하는 와이드 문자 수가 `szTypeDef`합니다.</span><span class="sxs-lookup"><span data-stu-id="79804-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="79804-110">[out] 형식 정의 수정 된 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="79804-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="79804-111">이 값은의 비트 마스크를 [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="79804-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="79804-112">[out] 형식 정의 또는 TypeRef 메타 데이터 토큰 요청 된 형식의 기본 형식을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="79804-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79804-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="79804-113">Requirements</span></span>  
 <span data-ttu-id="79804-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="79804-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79804-115">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="79804-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="79804-116">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="79804-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="79804-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="79804-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="79804-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="79804-118">See also</span></span>

- [<span data-ttu-id="79804-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="79804-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="79804-120">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="79804-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
