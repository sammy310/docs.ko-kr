---
description: '자세히 알아보기: IMetaDataImport:: GetUserString 메서드'
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
ms.openlocfilehash: 074d196c74be30f5879410ad44b9bb5c096eb153
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789101"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="8eab2-103">IMetaDataImport::GetUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="8eab2-103">IMetaDataImport::GetUserString Method</span></span>

<span data-ttu-id="8eab2-104">지정한 메타데이터 토큰이 나타내는 리터럴 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8eab2-104">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eab2-105">구문</span><span class="sxs-lookup"><span data-stu-id="8eab2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8eab2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8eab2-106">Parameters</span></span>  

 `stk`  
 <span data-ttu-id="8eab2-107">진행 연결 된 문자열을 반환할 문자열 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8eab2-107">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="8eab2-108">제한이 요청 된 문자열의 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="8eab2-108">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="8eab2-109">진행 요청 된의 최대 와이드 문자 크기입니다 `szString` .</span><span class="sxs-lookup"><span data-stu-id="8eab2-109">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="8eab2-110">제한이 반환 된의 와이드 문자 크기입니다 `szString` .</span><span class="sxs-lookup"><span data-stu-id="8eab2-110">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eab2-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8eab2-111">Requirements</span></span>  

 <span data-ttu-id="8eab2-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8eab2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8eab2-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8eab2-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8eab2-114">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8eab2-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8eab2-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eab2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eab2-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8eab2-116">See also</span></span>

- [<span data-ttu-id="8eab2-117">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8eab2-117">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="8eab2-118">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8eab2-118">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
