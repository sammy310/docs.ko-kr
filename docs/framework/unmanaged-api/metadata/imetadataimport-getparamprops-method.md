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
ms.openlocfilehash: a16621f4c9b06f049239dc4e2335d70a167dd756
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729267"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="40d86-102">IMetaDataImport::GetParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="40d86-102">IMetaDataImport::GetParamProps Method</span></span>

<span data-ttu-id="40d86-103">지정한 ParamDef 토큰이 참조하는 매개 변수에 대한 메타데이터 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="40d86-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40d86-104">구문</span><span class="sxs-lookup"><span data-stu-id="40d86-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="40d86-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40d86-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="40d86-106">진행 메타 데이터를 반환할 매개 변수를 나타내는 ParamDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="40d86-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="40d86-107">제한이 매개 변수를 사용 하는 메서드를 나타내는 MethodDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="40d86-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="40d86-108">제한이 메서드 인수 목록에 있는 매개 변수의 서 수 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="40d86-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="40d86-109">제한이 매개 변수의 이름을 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="40d86-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="40d86-110">진행 에서 요청 된 크기 (와이드 문자) `szName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="40d86-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="40d86-111">제한이 의 와이드 문자에서 반환 되는 크기입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="40d86-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="40d86-112">제한이 매개 변수와 연결 된 특성 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="40d86-112">[out] A pointer to any attribute flags associated with the parameter.</span></span> <span data-ttu-id="40d86-113">값의 비트 마스크입니다 `CorParamAttr` .</span><span class="sxs-lookup"><span data-stu-id="40d86-113">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="40d86-114">제한이 매개 변수가 임을 지정 하는 플래그에 대 한 포인터입니다 <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="40d86-114">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="40d86-115">제한이 매개 변수에서 반환 하는 상수 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="40d86-115">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="40d86-116">제한이 `ppValue` 와이드 문자 단위의 크기 이거나, `ppValue` 가 문자열을 포함 하지 않는 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="40d86-116">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40d86-117">설명</span><span class="sxs-lookup"><span data-stu-id="40d86-117">Remarks</span></span>

<span data-ttu-id="40d86-118">매개 변수의 시퀀스 값은 `pulSequence` 1로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="40d86-118">The sequence values in `pulSequence` begin with 1 for parameters.</span></span> <span data-ttu-id="40d86-119">반환 값의 시퀀스 번호는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="40d86-119">A return value has a sequence number of 0.</span></span>

## <a name="requirements"></a><span data-ttu-id="40d86-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40d86-120">Requirements</span></span>  

 <span data-ttu-id="40d86-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40d86-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40d86-122">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="40d86-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="40d86-123">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40d86-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="40d86-124">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40d86-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40d86-125">참조</span><span class="sxs-lookup"><span data-stu-id="40d86-125">See also</span></span>

- [<span data-ttu-id="40d86-126">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40d86-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="40d86-127">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40d86-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
