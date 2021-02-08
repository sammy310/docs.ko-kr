---
description: '자세히 알아보기: IMetaDataImport:: Is유효한 토큰 메서드'
title: IMetaDataImport::IsValidToken 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsValidToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type:
- apiref
ms.openlocfilehash: 68589496213c93f81cfbd0992f9b210e03d6f178
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789062"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="d57f6-103">IMetaDataImport::IsValidToken 메서드</span><span class="sxs-lookup"><span data-stu-id="d57f6-103">IMetaDataImport::IsValidToken Method</span></span>

<span data-ttu-id="d57f6-104">지정한 토큰이 코드 개체에 대한 유효한 참조를 포함하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d57f6-104">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d57f6-105">구문</span><span class="sxs-lookup"><span data-stu-id="d57f6-105">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d57f6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d57f6-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="d57f6-107">진행 참조 유효성 검사에 사용할 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d57f6-107">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d57f6-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="d57f6-108">Return Value</span></span>  

 <span data-ttu-id="d57f6-109">`true``tk`가 현재 범위 내의 유효한 메타 데이터 토큰 인 경우</span><span class="sxs-lookup"><span data-stu-id="d57f6-109">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="d57f6-110">그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="d57f6-110">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d57f6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d57f6-111">Requirements</span></span>  

 <span data-ttu-id="d57f6-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d57f6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d57f6-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d57f6-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d57f6-114">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d57f6-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d57f6-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d57f6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d57f6-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d57f6-116">See also</span></span>

- [<span data-ttu-id="d57f6-117">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d57f6-117">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="d57f6-118">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d57f6-118">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
