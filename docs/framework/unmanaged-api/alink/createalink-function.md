---
description: '자세히 알아보기: CreateALink 함수'
title: CreateALink 함수
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
ms.openlocfilehash: cf34ae8d38a8339f539c770df8f5dd14e4a3e4b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638368"
---
# <a name="createalink-function"></a><span data-ttu-id="6adda-103">CreateALink 함수</span><span class="sxs-lookup"><span data-stu-id="6adda-103">CreateALink Function</span></span>

<span data-ttu-id="6adda-104">어셈블리 링커의 인스턴스를 만들고 지정 된 인터페이스에 대 한 포인터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6adda-104">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6adda-105">구문</span><span class="sxs-lookup"><span data-stu-id="6adda-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6adda-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6adda-106">Parameters</span></span>  
  
|<span data-ttu-id="6adda-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6adda-107">Parameter</span></span>|<span data-ttu-id="6adda-108">설명</span><span class="sxs-lookup"><span data-stu-id="6adda-108">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="6adda-109">어셈블리 링커 인터페이스 중 하나의 물리적 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6adda-109">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="6adda-110">성공적으로 완료 되 면 인터페이스에 대 한 포인터를 포함 하는 위치입니다 `riid` .</span><span class="sxs-lookup"><span data-stu-id="6adda-110">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6adda-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6adda-111">Requirements</span></span>  

 <span data-ttu-id="6adda-112">**라이브러리**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="6adda-112">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6adda-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6adda-113">See also</span></span>

- [<span data-ttu-id="6adda-114">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="6adda-114">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
