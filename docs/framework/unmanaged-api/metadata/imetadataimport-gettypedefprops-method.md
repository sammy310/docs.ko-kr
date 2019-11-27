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
ms.openlocfilehash: c9ac624e17223def206e86fd92ee4fd2de7f6082
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436754"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="a3f98-102">IMetaDataImport::GetTypeDefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="a3f98-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="a3f98-103">지정 된 TypeDef 토큰이 나타내는 <xref:System.Type>에 대 한 메타 데이터 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3f98-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3f98-104">구문</span><span class="sxs-lookup"><span data-stu-id="a3f98-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="a3f98-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a3f98-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="a3f98-106">진행 메타 데이터를 반환할 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a3f98-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="a3f98-107">제한이 형식 이름을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="a3f98-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="a3f98-108">진행 `szTypeDef`의 와이드 문자 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a3f98-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="a3f98-109">제한이 `szTypeDef`에서 반환 되는 와이드 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3f98-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="a3f98-110">제한이 형식 정의를 수정 하는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a3f98-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="a3f98-111">이 값은 [Cortypeattr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) 열거형의 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="a3f98-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="a3f98-112">제한이 요청 된 형식의 기본 형식을 나타내는 TypeDef 또는 TypeRef 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a3f98-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3f98-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3f98-113">Requirements</span></span>  
 <span data-ttu-id="a3f98-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3f98-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3f98-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="a3f98-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a3f98-116">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3f98-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a3f98-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3f98-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f98-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="a3f98-118">See also</span></span>

- [<span data-ttu-id="a3f98-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a3f98-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a3f98-120">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a3f98-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
