---
title: IMetaDataImport::EnumMemberRefs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
ms.openlocfilehash: d8b02e85efc2cd7364690dd42104a313ba6ec272
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711457"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="d6aed-102">IMetaDataImport::EnumMemberRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="d6aed-102">IMetaDataImport::EnumMemberRefs Method</span></span>

<span data-ttu-id="d6aed-103">지정한 형식의 멤버를 나타내는 MemberRef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="d6aed-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6aed-104">구문</span><span class="sxs-lookup"><span data-stu-id="d6aed-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,
   [in]   mdToken        tkParent,
   [out]  mdMemberRef    rMemberRefs[],
   [in]   ULONG          cMax,
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6aed-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d6aed-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="d6aed-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d6aed-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="d6aed-107">진행 멤버가 열거 될 형식에 대 한 TypeDef, TypeRef, MethodDef 또는 ModuleRef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d6aed-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="d6aed-108">제한이 MemberRef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d6aed-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d6aed-109">[in] `rMemberRefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d6aed-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d6aed-110">제한이 에서 반환 된 실제 MemberRef 토큰 수입니다 `rMemberRefs` .</span><span class="sxs-lookup"><span data-stu-id="d6aed-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6aed-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="d6aed-111">Return Value</span></span>  
  
|<span data-ttu-id="d6aed-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d6aed-112">HRESULT</span></span>|<span data-ttu-id="d6aed-113">설명</span><span class="sxs-lookup"><span data-stu-id="d6aed-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d6aed-114">`EnumMemberRefs` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6aed-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d6aed-115">열거할 MemberRef 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6aed-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="d6aed-116">`pcTokens`이 경우은 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6aed-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d6aed-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d6aed-117">Requirements</span></span>  

 <span data-ttu-id="d6aed-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6aed-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6aed-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d6aed-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d6aed-120">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6aed-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d6aed-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6aed-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6aed-122">참조</span><span class="sxs-lookup"><span data-stu-id="d6aed-122">See also</span></span>

- [<span data-ttu-id="d6aed-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6aed-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="d6aed-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6aed-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
