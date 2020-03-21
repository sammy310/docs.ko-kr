---
title: IMetaDataImport::GetMemberRefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
ms.openlocfilehash: a61254ba751e47b0089a3f7528aca337a32e2db3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175371"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="6c128-102">IMetaDataImport::GetMemberRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="6c128-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="6c128-103">지정한 토큰이 참조하는 멤버와 연결된 메타데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6c128-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c128-104">구문</span><span class="sxs-lookup"><span data-stu-id="6c128-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,
   [out] mdToken           *ptk,
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pbSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c128-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6c128-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="6c128-106">【인】 멤버 참조 토큰에 대 한 관련 된 메타 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c128-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="6c128-107">【아웃】 멤버를 선언하는 클래스를 나타내는 TypeDef 또는 TypeRef 또는 멤버를 선언하는 모듈 클래스또는 멤버를 나타내는 MethodDef를 나타내는 ModuleRef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6c128-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="6c128-108">【아웃】 멤버 이름에 대한 문자열 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="6c128-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="6c128-109">【인】 의 넓은 문자로 `szMember`요청된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6c128-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="6c128-110">【아웃】 의 넓은 문자로 `szMember`반환 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6c128-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="6c128-111">【아웃】 멤버에 대한 이진 메타데이터 시그니처에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c128-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="6c128-112">【아웃】 의 바이트 크기입니다. `ppvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="6c128-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c128-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c128-113">Requirements</span></span>  
 <span data-ttu-id="6c128-114">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c128-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c128-115">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="6c128-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6c128-116">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6c128-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6c128-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c128-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c128-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c128-118">See also</span></span>

- [<span data-ttu-id="6c128-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c128-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6c128-120">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c128-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
