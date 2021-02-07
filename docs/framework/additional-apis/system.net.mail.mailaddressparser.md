---
description: '자세히 알아보기: MailAddressParser 클래스'
title: MailAddressParser 클래스 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.MailAddressParser
- System.Net.Mail.MailAddressParser.ParseAddress
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 5ad534e731e283f5449b3b8cc8e87628716da9b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699768"
---
# <a name="mailaddressparser-class"></a><span data-ttu-id="f147a-103">MailAddressParser 클래스</span><span class="sxs-lookup"><span data-stu-id="f147a-103">MailAddressParser class</span></span>

<span data-ttu-id="f147a-104">RFC 2822에 설명 된 대로 전자 메일 주소를 구문 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="f147a-104">Parses email addresses as described in RFC 2822.</span></span> <span data-ttu-id="f147a-105">이 클래스는 상속될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f147a-105">This class cannot be inherited.</span></span>

```csharp
internal static class MailAddressParser
```

> [!WARNING]
> <span data-ttu-id="f147a-106">이 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f147a-106">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="f147a-107">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f147a-107">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="parseaddress-method"></a><span data-ttu-id="f147a-108">ParseAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="f147a-108">ParseAddress method</span></span>

<span data-ttu-id="f147a-109">지정 된 문자열에서 단일 전자 메일 주소를 구문 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="f147a-109">Parses a single email address from the specified string.</span></span>

```csharp
internal static MailAddress ParseAddress(string data)
```

### <a name="parameters"></a><span data-ttu-id="f147a-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f147a-110">Parameters</span></span>

<span data-ttu-id="f147a-111">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="f147a-111">`data` <xref:System.String></span></span>

<span data-ttu-id="f147a-112">구문 분석할 전자 메일 주소를 포함 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f147a-112">The string that contains an email address to be parsed.</span></span>

### <a name="return-value"></a><span data-ttu-id="f147a-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="f147a-113">Return value</span></span>

<xref:System.Net.Mail.MailAddress>

<span data-ttu-id="f147a-114">유효한 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="f147a-114">A valid email address.</span></span>

### <a name="exceptions"></a><span data-ttu-id="f147a-115">예외</span><span class="sxs-lookup"><span data-stu-id="f147a-115">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="f147a-116">전자 메일 주소가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f147a-116">The email address is invalid.</span></span>

## <a name="requirements"></a><span data-ttu-id="f147a-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f147a-117">Requirements</span></span>

<span data-ttu-id="f147a-118">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="f147a-118">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="f147a-119">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="f147a-119">**Assembly:** System (in System.dll)</span></span>
