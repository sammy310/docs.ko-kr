---
title: IMetaDataImport::GetParamProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
ms.openlocfilehash: bb73ccdd9eee4b5a655a56b5d6757e0c6003fbc9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437130"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="fd7d1-102">IMetaDataImport::GetParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="fd7d1-102">IMetaDataImport::GetParamProps Method</span></span>
<span data-ttu-id="fd7d1-103">지정한 ParamDef 토큰이 참조하는 매개 변수에 대한 메타데이터 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fd7d1-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd7d1-104">구문</span><span class="sxs-lookup"><span data-stu-id="fd7d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd7d1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fd7d1-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="fd7d1-106">진행 메타 데이터를 반환할 매개 변수를 나타내는 ParamDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="fd7d1-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="fd7d1-107">제한이 매개 변수를 사용 하는 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fd7d1-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="fd7d1-108">제한이 메서드 인수 목록에 있는 매개 변수의 서 수 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="fd7d1-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="fd7d1-109">제한이 매개 변수의 이름을 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="fd7d1-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="fd7d1-110">진행 `szName`의 와이드 문자에서 요청 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="fd7d1-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="fd7d1-111">제한이 `szName`의 와이드 문자에서 반환 되는 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="fd7d1-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="fd7d1-112">제한이 매개 변수와 연결 된 특성 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fd7d1-112">[out] A pointer to any attribute flags associated with the parameter.</span></span> <span data-ttu-id="fd7d1-113">`CorParamAttr` 값의 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="fd7d1-113">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="fd7d1-114">제한이 매개 변수가 <xref:System.ValueType>임을 지정 하는 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fd7d1-114">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="fd7d1-115">제한이 매개 변수에서 반환 하는 상수 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fd7d1-115">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="fd7d1-116">제한이 와이드 문자 `ppValue` 크기 이거나 `ppValue`에 문자열이 없는 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="fd7d1-116">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd7d1-117">주의</span><span class="sxs-lookup"><span data-stu-id="fd7d1-117">Remarks</span></span>

<span data-ttu-id="fd7d1-118">매개 변수에 대 한 `pulSequence`의 시퀀스 값은 1로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd7d1-118">The sequence values in `pulSequence` begin with 1 for parameters.</span></span> <span data-ttu-id="fd7d1-119">반환 값의 시퀀스 번호는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="fd7d1-119">A return value has a sequence number of 0.</span></span>

## <a name="requirements"></a><span data-ttu-id="fd7d1-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd7d1-120">Requirements</span></span>  
 <span data-ttu-id="fd7d1-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd7d1-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd7d1-122">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="fd7d1-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fd7d1-123">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd7d1-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fd7d1-124">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd7d1-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd7d1-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd7d1-125">See also</span></span>

- [<span data-ttu-id="fd7d1-126">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd7d1-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="fd7d1-127">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd7d1-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
