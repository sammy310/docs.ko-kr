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
ms.openlocfilehash: 1d6d66ea62cbf679f722f830b3638455001aedd6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437496"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="f2121-102">IMetaDataImport::GetMemberRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="f2121-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="f2121-103">지정한 토큰이 참조하는 멤버와 연결된 메타데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f2121-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2121-104">구문</span><span class="sxs-lookup"><span data-stu-id="f2121-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f2121-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f2121-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="f2121-106">진행 연결 된 메타 데이터를 반환할 MemberRef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f2121-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="f2121-107">제한이 TypeDef 또는 TypeRef 또는 멤버를 선언 하는 클래스를 나타내는 TypeSpec 토큰 또는 멤버를 선언 하는 모듈 클래스를 나타내는 ModuleRef 토큰 또는 멤버를 나타내는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f2121-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="f2121-108">제한이 멤버의 이름에 대 한 문자열 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="f2121-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="f2121-109">진행 `szMember`의 와이드 문자에서 요청 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f2121-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="f2121-110">제한이 `szMember`의 와이드 문자에서 반환 되는 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f2121-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="f2121-111">제한이 멤버의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f2121-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="f2121-112">제한이 `ppvSigBlob`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="f2121-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2121-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2121-113">Requirements</span></span>  
 <span data-ttu-id="f2121-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f2121-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2121-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="f2121-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2121-116">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2121-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f2121-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2121-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2121-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2121-118">See also</span></span>

- [<span data-ttu-id="f2121-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2121-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f2121-120">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2121-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
