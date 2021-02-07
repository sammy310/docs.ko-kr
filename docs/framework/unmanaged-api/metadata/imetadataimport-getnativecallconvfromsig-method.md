---
description: '자세히 알아보기: IMetaDataImport:: GetNativeCallConvFromSig 메서드'
title: IMetaDataImport::GetNativeCallConvFromSig 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNativeCallConvFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNativeCallConvFromSig
helpviewer_keywords:
- GetNativeCallConvFromSig method [.NET Framework metadata]
- IMetaDataImport::GetNativeCallConvFromSig method [.NET Framework metadata]
ms.assetid: 50e04026-4d4a-47d9-96c1-f4677d6d938b
topic_type:
- apiref
ms.openlocfilehash: 2fb5c347098f860f9ad32eab20c8b5bd6278f838
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677576"
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="6780b-103">IMetaDataImport::GetNativeCallConvFromSig 메서드</span><span class="sxs-lookup"><span data-stu-id="6780b-103">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>

<span data-ttu-id="6780b-104">지정한 서명 포인터가 나타내는 메서드에 대한 기본 호출 규칙을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6780b-104">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6780b-105">구문</span><span class="sxs-lookup"><span data-stu-id="6780b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6780b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6780b-106">Parameters</span></span>  

 `pvSig`  
 <span data-ttu-id="6780b-107">진행 호출 규칙을 반환할 메서드의 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6780b-107">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="6780b-108">진행 의 크기 (바이트) `pvSig` 입니다.</span><span class="sxs-lookup"><span data-stu-id="6780b-108">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="6780b-109">제한이 네이티브 호출 규칙에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6780b-109">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6780b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6780b-110">Requirements</span></span>  

 <span data-ttu-id="6780b-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6780b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6780b-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="6780b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6780b-113">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6780b-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6780b-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6780b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6780b-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6780b-115">See also</span></span>

- <xref:System.Runtime.InteropServices.CallingConvention>
- [<span data-ttu-id="6780b-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6780b-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6780b-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6780b-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
