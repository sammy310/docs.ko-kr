---
title: IMetaDataImport::GetUserString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetUserString
helpviewer_keywords:
- IMetaDataImport::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0fd3bb47-58b5-4083-b241-b9719df7a285
topic_type:
- apiref
ms.openlocfilehash: af3de5454ce3d4a763c216de6e8efdb39407457b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729137"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="07000-102">IMetaDataImport::GetUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="07000-102">IMetaDataImport::GetUserString Method</span></span>

<span data-ttu-id="07000-103">지정한 메타데이터 토큰이 나타내는 리터럴 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="07000-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07000-104">구문</span><span class="sxs-lookup"><span data-stu-id="07000-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07000-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="07000-105">Parameters</span></span>  

 `stk`  
 <span data-ttu-id="07000-106">진행 연결 된 문자열을 반환할 문자열 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="07000-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="07000-107">제한이 요청 된 문자열의 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="07000-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="07000-108">진행 요청 된의 최대 와이드 문자 크기입니다 `szString` .</span><span class="sxs-lookup"><span data-stu-id="07000-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="07000-109">제한이 반환 된의 와이드 문자 크기입니다 `szString` .</span><span class="sxs-lookup"><span data-stu-id="07000-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07000-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="07000-110">Requirements</span></span>  

 <span data-ttu-id="07000-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07000-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07000-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="07000-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07000-113">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07000-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="07000-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07000-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07000-115">참조</span><span class="sxs-lookup"><span data-stu-id="07000-115">See also</span></span>

- [<span data-ttu-id="07000-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07000-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="07000-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07000-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
