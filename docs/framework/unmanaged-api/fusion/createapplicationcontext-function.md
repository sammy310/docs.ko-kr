---
description: '자세한 정보: CreateApplicationContext 함수'
title: CreateApplicationContext 함수
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
ms.openlocfilehash: f192e1ccc371cb6d50e4a41a286c412825ee4181
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761184"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="b8757-103">CreateApplicationContext 함수</span><span class="sxs-lookup"><span data-stu-id="b8757-103">CreateApplicationContext Function</span></span>

<span data-ttu-id="b8757-104">이 함수는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b8757-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8757-105">구문</span><span class="sxs-lookup"><span data-stu-id="b8757-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8757-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b8757-106">Parameters</span></span>  

 `pName`  
 <span data-ttu-id="b8757-107">진행 친숙 한 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b8757-107">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="b8757-108">제한이 응용 프로그램 컨텍스트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b8757-108">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8757-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8757-109">Requirements</span></span>  

 <span data-ttu-id="b8757-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8757-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8757-111">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b8757-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b8757-112">**라이브러리:** Fusion.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8757-112">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="b8757-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8757-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8757-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8757-114">See also</span></span>

- [<span data-ttu-id="b8757-115">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8757-115">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="b8757-116">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="b8757-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="b8757-117">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="b8757-117">Global Assembly Cache</span></span>](../../app-domains/gac.md)
