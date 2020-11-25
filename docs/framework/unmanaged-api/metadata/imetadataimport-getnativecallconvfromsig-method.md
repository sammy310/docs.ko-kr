---
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
ms.openlocfilehash: d44ad493a786aaa35150515b7c254965490bd714
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701707"
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="0dbe6-102">IMetaDataImport::GetNativeCallConvFromSig 메서드</span><span class="sxs-lookup"><span data-stu-id="0dbe6-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>

<span data-ttu-id="0dbe6-103">지정한 서명 포인터가 나타내는 메서드에 대한 기본 호출 규칙을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0dbe6-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dbe6-104">구문</span><span class="sxs-lookup"><span data-stu-id="0dbe6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dbe6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0dbe6-105">Parameters</span></span>  

 `pvSig`  
 <span data-ttu-id="0dbe6-106">진행 호출 규칙을 반환할 메서드의 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0dbe6-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="0dbe6-107">진행 의 크기 (바이트) `pvSig` 입니다.</span><span class="sxs-lookup"><span data-stu-id="0dbe6-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="0dbe6-108">제한이 네이티브 호출 규칙에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0dbe6-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dbe6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0dbe6-109">Requirements</span></span>  

 <span data-ttu-id="0dbe6-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0dbe6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dbe6-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="0dbe6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0dbe6-112">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dbe6-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0dbe6-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dbe6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dbe6-114">참조</span><span class="sxs-lookup"><span data-stu-id="0dbe6-114">See also</span></span>

- <xref:System.Runtime.InteropServices.CallingConvention>
- [<span data-ttu-id="0dbe6-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0dbe6-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="0dbe6-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0dbe6-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
