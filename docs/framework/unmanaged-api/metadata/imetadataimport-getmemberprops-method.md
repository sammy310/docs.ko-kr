---
description: '자세히 알아보기: IMetaDataImport:: GetMemberProps 메서드'
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
ms.openlocfilehash: 073c8fae06c3df69f0b3152b109417b818637d1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783900"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="5c283-103">IMetaDataImport::GetMemberProps 메서드</span><span class="sxs-lookup"><span data-stu-id="5c283-103">IMetaDataImport::GetMemberProps Method</span></span>

<span data-ttu-id="5c283-104">지정 된 <xref:System.Type> 메타 데이터 토큰에서 참조 하는 멤버의 이름, 이진 서명 및 상대 가상 주소를 포함 하 여, 지정 된 멤버 정의에 대 한 메타 데이터에 저장 된 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5c283-104">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="5c283-105">이는 간단한 도우미 메서드입니다. *mb* 가 MethodDef 인 경우 **getmethodprops** 이 호출 됩니다. *mb* 가 FieldDef 인 경우 **getfieldprops** 가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c283-105">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="5c283-106">자세한 내용은 다음 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5c283-106">See these other methods for details.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="5c283-107">구문</span><span class="sxs-lookup"><span data-stu-id="5c283-107">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5c283-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5c283-108">Parameters</span></span>  

 `mb`  
 <span data-ttu-id="5c283-109">진행 연결 된 메타 데이터를 가져올 멤버를 참조 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5c283-109">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="5c283-110">제한이 멤버의 클래스를 나타내는 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5c283-110">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="5c283-111">제한이 멤버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5c283-111">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="5c283-112">진행 버퍼의 와이드 문자 크기 `szMember` 입니다.</span><span class="sxs-lookup"><span data-stu-id="5c283-112">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="5c283-113">제한이 반환 된 이름의 와이드 문자 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5c283-113">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="5c283-114">제한이 멤버에 적용 된 모든 플래그 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5c283-114">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="5c283-115">제한이 멤버의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5c283-115">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="5c283-116">제한이 의 크기 (바이트) `ppvSigBlob` 입니다.</span><span class="sxs-lookup"><span data-stu-id="5c283-116">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="5c283-117">제한이 멤버의 상대 가상 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5c283-117">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="5c283-118">제한이 멤버와 연결 된 모든 메서드 구현 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="5c283-118">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="5c283-119">제한이 을 표시 하는 플래그입니다 <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="5c283-119">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="5c283-120">값 중 하나입니다 `ELEMENT_TYPE_*` .</span><span class="sxs-lookup"><span data-stu-id="5c283-120">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="5c283-121">제한이 이 멤버에서 반환 하는 상수 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5c283-121">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="5c283-122">제한이 의 문자 크기 `ppValue` 이거나, `ppValue` 가 문자열을 포함 하지 않는 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="5c283-122">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c283-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c283-123">Requirements</span></span>  

 <span data-ttu-id="5c283-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c283-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c283-125">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="5c283-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c283-126">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c283-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c283-127">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c283-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c283-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c283-128">See also</span></span>

- [<span data-ttu-id="5c283-129">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c283-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="5c283-130">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c283-130">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
