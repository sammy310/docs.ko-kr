---
description: '자세한 정보: ComNetOS 클래스'
title: ComNetOS 클래스 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ComNetOS
- System.Net.ComNetOS.IsWin7orLater
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 7376fe4a5e02818907cb71573451fffb3a3667cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802530"
---
# <a name="comnetos-class"></a><span data-ttu-id="058c5-103">ComNetOS 클래스</span><span class="sxs-lookup"><span data-stu-id="058c5-103">ComNetOS class</span></span>

<span data-ttu-id="058c5-104">현재 운영 체제에 대 한 정보 (예: 버전 및 설치 유형 (클라이언트 또는 서버))를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="058c5-104">Provides information about the current operating system, such as its version and installation type (client or server).</span></span> <span data-ttu-id="058c5-105">이 클래스는 상속될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="058c5-105">This class cannot be inherited.</span></span>
  
```csharp  
internal static class ComNetOS
```

> [!WARNING]
> <span data-ttu-id="058c5-106">이 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="058c5-106">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="058c5-107">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="058c5-107">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="iswin7orlater-field"></a><span data-ttu-id="058c5-108">IsWin7orLater 필드</span><span class="sxs-lookup"><span data-stu-id="058c5-108">IsWin7orLater field</span></span>

<span data-ttu-id="058c5-109">운영 체제 버전이 Windows 7 이상 인지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="058c5-109">Specifies whether the operating system version is Windows 7 or later.</span></span>

```csharp
internal static readonly bool IsWin7orLater
```

## <a name="requirements"></a><span data-ttu-id="058c5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="058c5-110">Requirements</span></span>

<span data-ttu-id="058c5-111">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="058c5-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="058c5-112">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="058c5-112">**Assembly:** System (in System.dll)</span></span>
