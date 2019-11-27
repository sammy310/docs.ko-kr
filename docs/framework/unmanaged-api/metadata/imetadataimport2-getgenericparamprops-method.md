---
title: IMetaDataImport2::GetGenericParamProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
ms.openlocfilehash: a8c5dd263401002deaee3d21f1e41b41a29faec2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427303"
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="87792-102">IMetaDataImport2::GetGenericParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="87792-102">IMetaDataImport2::GetGenericParamProps Method</span></span>
<span data-ttu-id="87792-103">지정 된 토큰이 나타내는 제네릭 매개 변수와 연결 된 메타 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="87792-103">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87792-104">구문</span><span class="sxs-lookup"><span data-stu-id="87792-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87792-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="87792-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="87792-106">진행 메타 데이터를 반환할 제네릭 매개 변수를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="87792-106">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="87792-107">제한이 부모 생성자 또는 메서드에서 `Type` 매개 변수의 서 수 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="87792-107">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="87792-108">제한이 제네릭 매개 변수에 대 한 `Type`를 설명 하는 [Corgenericparamattr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="87792-108">[out] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="87792-109">제한이 매개 변수의 소유자를 나타내는 TypeDef 또는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="87792-109">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="87792-110">제한이 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="87792-110">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="87792-111">제한이 제네릭 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="87792-111">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="87792-112">진행 `wzName` 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="87792-112">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="87792-113">제한이 반환 된 이름의 크기 (와이드 문자)입니다.</span><span class="sxs-lookup"><span data-stu-id="87792-113">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87792-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87792-114">Requirements</span></span>  
 <span data-ttu-id="87792-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87792-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87792-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="87792-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="87792-117">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87792-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="87792-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87792-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87792-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="87792-119">See also</span></span>

- [<span data-ttu-id="87792-120">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87792-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="87792-121">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87792-121">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
