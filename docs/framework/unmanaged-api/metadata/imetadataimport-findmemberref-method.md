---
description: '자세히 알아보기: IMetaDataImport:: FindMemberRef 메서드'
title: IMetaDataImport::FindMemberRef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
ms.openlocfilehash: 301d4dc88b36ca2284ca3b8d70444820befdc0aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745582"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="753cc-103">IMetaDataImport::FindMemberRef 메서드</span><span class="sxs-lookup"><span data-stu-id="753cc-103">IMetaDataImport::FindMemberRef Method</span></span>

<span data-ttu-id="753cc-104">지정 된 <xref:System.Type> 및 메타 데이터 서명을 가진 지정 된로 묶인 멤버 참조의 MemberRef 토큰에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="753cc-104">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="753cc-105">구문</span><span class="sxs-lookup"><span data-stu-id="753cc-105">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="753cc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="753cc-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="753cc-107">진행 검색할 멤버 참조를 포함 하는 클래스 또는 인터페이스의 TypeRef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="753cc-107">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="753cc-108">이 값이 이면 `mdTokenNil` 전역 변수나 전역 함수 참조에 대해 조회가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="753cc-108">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="753cc-109">진행 검색할 멤버 참조의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="753cc-109">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="753cc-110">진행 멤버 참조의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="753cc-110">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="753cc-111">진행 의 크기 (바이트) `pvSigBlob` 입니다.</span><span class="sxs-lookup"><span data-stu-id="753cc-111">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="753cc-112">제한이 일치 하는 MemberRef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="753cc-112">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="753cc-113">설명</span><span class="sxs-lookup"><span data-stu-id="753cc-113">Remarks</span></span>  

 <span data-ttu-id="753cc-114">바깥쪽 클래스 또는 인터페이스 ( `td` ), 이름 ( `szName` ) 및 선택적으로 시그니처 ()를 사용 하 여 멤버를 지정 `pvSigBlob` 합니다.</span><span class="sxs-lookup"><span data-stu-id="753cc-114">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="753cc-115">서명이 특정 범위에 바인딩되기 때문에에 전달 된 시그니처는 `FindMemberRef` 현재 범위에서 생성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="753cc-115">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="753cc-116">시그니처에는 바깥쪽 클래스 또는 값 형식을 식별 하는 토큰이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="753cc-116">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="753cc-117">토큰은 로컬 TypeDef 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="753cc-117">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="753cc-118">현재 범위의 컨텍스트 외부에서 런타임 서명을 작성 하 고 해당 서명을에 대 한 입력으로 사용할 수 없습니다 `FindMemberRef` .</span><span class="sxs-lookup"><span data-stu-id="753cc-118">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="753cc-119">`FindMemberRef` 클래스 또는 인터페이스에서 직접 정의 된 멤버 참조만 찾습니다. 상속 된 멤버 참조를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="753cc-119">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="753cc-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="753cc-120">Requirements</span></span>  

 <span data-ttu-id="753cc-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="753cc-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="753cc-122">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="753cc-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="753cc-123">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="753cc-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="753cc-124">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="753cc-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="753cc-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="753cc-125">See also</span></span>

- [<span data-ttu-id="753cc-126">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="753cc-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="753cc-127">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="753cc-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
