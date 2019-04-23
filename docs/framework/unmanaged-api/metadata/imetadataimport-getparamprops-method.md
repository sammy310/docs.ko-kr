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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05ac8efed8c0a905d2cfad433348a99fe578eeae
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153181"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="ac3cc-102">IMetaDataImport::GetParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="ac3cc-102">IMetaDataImport::GetParamProps Method</span></span>
<span data-ttu-id="ac3cc-103">지정한 ParamDef 토큰이 참조하는 매개 변수에 대한 메타데이터 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac3cc-104">구문</span><span class="sxs-lookup"><span data-stu-id="ac3cc-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="ac3cc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ac3cc-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ac3cc-106">[in] 에 대 한 메타 데이터를 반환 하려면 매개 변수를 나타내는 ParamDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="ac3cc-107">[out] 매개 변수를 사용 하는 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="ac3cc-108">[out] 메서드 인수 목록에 있는 매개 변수의 서 수 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="ac3cc-109">[out] 매개 변수의 이름을 포함 하도록 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ac3cc-110">[in] 요청된 된 크기의 와이드 문자에서 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ac3cc-111">[out] 반환 되는 크기의 와이드 문자에서 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="ac3cc-112">[out] 매개 변수를 사용 하 여 연결 된 모든 특성 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-112">[out] A pointer to any attribute flags associated with the parameter.</span></span> <span data-ttu-id="ac3cc-113">이 비트 마스크의 `CorParamAttr` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-113">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="ac3cc-114">[out] 매개 변수가 지정 하는 플래그에 대 한 포인터를 <xref:System.ValueType>입니다.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-114">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="ac3cc-115">[out] 매개 변수에서 반환 하는 상수 문자열 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-115">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="ac3cc-116">[out] 크기인 `ppValue` 와이드 문자인 경우 0에 `ppValue` 문자열이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-116">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac3cc-117">설명</span><span class="sxs-lookup"><span data-stu-id="ac3cc-117">Remarks</span></span>

<span data-ttu-id="ac3cc-118">시퀀스 값 `pulSequence` 매개 변수에 대 한 1부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-118">The sequence values in `pulSequence` begin with 1 for parameters.</span></span> <span data-ttu-id="ac3cc-119">반환 값에 0의 시퀀스 번호가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-119">A return value has a sequence number of 0.</span></span>

## <a name="requirements"></a><span data-ttu-id="ac3cc-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac3cc-120">Requirements</span></span>  
 <span data-ttu-id="ac3cc-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ac3cc-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac3cc-122">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ac3cc-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ac3cc-123">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ac3cc-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac3cc-124">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac3cc-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac3cc-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac3cc-125">See also</span></span>

- [<span data-ttu-id="ac3cc-126">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac3cc-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ac3cc-127">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac3cc-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
