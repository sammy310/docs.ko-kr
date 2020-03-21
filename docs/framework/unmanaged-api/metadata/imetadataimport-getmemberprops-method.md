---
title: IMetaDataImport::GetMemberProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
ms.openlocfilehash: 72e14ea0414ebdeb8f54a4bdef8ce5208fc8ef72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177225"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="7181d-102">IMetaDataImport::GetMemberProps 메서드</span><span class="sxs-lookup"><span data-stu-id="7181d-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="7181d-103">지정된 메타데이터 토큰에서 참조하는 멤버의 이름, 이진 서명 및 상대 <xref:System.Type> 가상 주소를 포함하여 지정된 멤버 정의에 대한 메타데이터에 저장된 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7181d-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="7181d-104">이것은 간단한 도우미 메서드: *mb는* MethodDef 인 경우 **GetMethodProps** 가 호출 됩니다. *mb가* 필드데프인 경우 **GetFieldProps가 호출됩니다.**</span><span class="sxs-lookup"><span data-stu-id="7181d-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="7181d-105">자세한 내용은 다음 다른 방법을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7181d-105">See these other methods for details.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="7181d-106">구문</span><span class="sxs-lookup"><span data-stu-id="7181d-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pcbSigBlob,
   [out] ULONG             *pulCodeRVA,
   [out] DWORD             *pdwImplFlags,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7181d-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7181d-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="7181d-108">【인】 관련 메타데이터를 가져오는 멤버를 참조하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7181d-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="7181d-109">【아웃】 멤버의 클래스를 나타내는 메타데이터 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7181d-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="7181d-110">【아웃】 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7181d-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="7181d-111">【인】 버퍼의 넓은 문자의 `szMember` 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="7181d-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="7181d-112">【아웃】 반환 된 이름의 넓은 문자의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="7181d-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="7181d-113">【아웃】 멤버에 적용된 모든 플래그 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7181d-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="7181d-114">【아웃】 멤버의 이진 메타데이터 시그니처에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7181d-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="7181d-115">【아웃】 의 바이트 크기입니다. `ppvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="7181d-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="7181d-116">【아웃】 멤버의 상대 가상 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7181d-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="7181d-117">【아웃】 멤버와 연결된 메서드 구현 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="7181d-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="7181d-118">【아웃】 을 표시하는 플래그입니다. <xref:System.ValueType></span><span class="sxs-lookup"><span data-stu-id="7181d-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="7181d-119">그것은 `ELEMENT_TYPE_*` 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7181d-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="7181d-120">【아웃】 이 멤버에서 반환되는 상수 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7181d-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="7181d-121">【아웃】 문자열을 보유하지 `ppValue`않는 경우 `ppValue` 의 문자 크기 또는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="7181d-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7181d-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7181d-122">Requirements</span></span>  
 <span data-ttu-id="7181d-123">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7181d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7181d-124">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="7181d-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7181d-125">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7181d-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7181d-126">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7181d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7181d-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7181d-127">See also</span></span>

- [<span data-ttu-id="7181d-128">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7181d-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7181d-129">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7181d-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
