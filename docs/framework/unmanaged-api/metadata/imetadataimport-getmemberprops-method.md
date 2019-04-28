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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83dec9b6ed3b1e538e0f1b7d13a33b8bdbc1cf54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777730"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="fd365-102">IMetaDataImport::GetMemberProps 메서드</span><span class="sxs-lookup"><span data-stu-id="fd365-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="fd365-103">이름, 이진 서명 및 상대 가상 주소를 포함 하 여 지정 된 멤버 정의 대 한 메타 데이터에 저장 된 정보를 가져옵니다는 <xref:System.Type> 지정 된 메타 데이터 토큰에서 참조 하는 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="fd365-104">간단한 도우미 메서드입니다.: 하는 경우 *mb* MethodDef, 이면 **GetMethodProps** 가 호출 되는 경우 *mb* 이면 한 FieldDef **GetFieldProps** 가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="fd365-105">이러한 세부 정보는 다른 방법을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-105">See these other methods for details.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="fd365-106">구문</span><span class="sxs-lookup"><span data-stu-id="fd365-106">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="fd365-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fd365-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="fd365-108">[in] 연결 된 메타 데이터를 가져올 멤버를 참조 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="fd365-109">[out] 멤버의 클래스를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="fd365-110">[out] 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="fd365-111">[in] 와이드 문자에서 크기를 `szMember` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="fd365-112">[out] 반환 된 이름의 와이드 문자 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="fd365-113">[out] 모든 플래그 멤버에 적용 되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="fd365-114">[out] 멤버의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="fd365-115">[out] 크기 (바이트) `ppvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="fd365-116">[out] 멤버의 상대 가상 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="fd365-117">[out] 멤버에 연결 된 모든 메서드 구현 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="fd365-118">[out] 표시 하는 플래그를 <xref:System.ValueType>입니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="fd365-119">중 하나는 `ELEMENT_TYPE_*` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="fd365-120">[out] 이 멤버에 의해 반환 되는 상수 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="fd365-121">[out] 크기의 문자 `ppValue`, 또는 경우에는 0 `ppValue` 문자열이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd365-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd365-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd365-122">Requirements</span></span>  
 <span data-ttu-id="fd365-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd365-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd365-124">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fd365-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fd365-125">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="fd365-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fd365-126">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd365-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd365-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="fd365-127">See also</span></span>

- [<span data-ttu-id="fd365-128">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd365-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="fd365-129">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd365-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
