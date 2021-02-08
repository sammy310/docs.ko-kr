---
description: ISymUnmanagedAsyncMethodPropertiesWriter::D efineKickoffMethod 메서드에 대해 자세히 알아보세요.
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: 7333823bce27eace4e9cb988ac31252743cca952
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790232"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="70572-103">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="70572-103">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>

<span data-ttu-id="70572-104">비동기 작업을 시작 하는 시작 메서드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="70572-104">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70572-105">구문</span><span class="sxs-lookup"><span data-stu-id="70572-105">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70572-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="70572-106">Parameters</span></span>  
  
|<span data-ttu-id="70572-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="70572-107">Parameter</span></span>|<span data-ttu-id="70572-108">설명</span><span class="sxs-lookup"><span data-stu-id="70572-108">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="70572-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="70572-109">Return Value</span></span>  

 <span data-ttu-id="70572-110">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="70572-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70572-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70572-111">Requirements</span></span>  

 <span data-ttu-id="70572-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="70572-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70572-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70572-113">See also</span></span>

- [<span data-ttu-id="70572-114">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70572-114">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
