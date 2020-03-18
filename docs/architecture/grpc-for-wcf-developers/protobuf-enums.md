---
title: 프로토부프 열거 - WCF 개발자를 위한 gRPC
description: Protobuf에서 열거를 선언하고 사용하는 방법을 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: 2177f568a671fa0e651625c6e025ac70c243feb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148077"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="a3654-103">Protobuf 열거형</span><span class="sxs-lookup"><span data-stu-id="a3654-103">Protobuf enumerations</span></span>

<span data-ttu-id="a3654-104">Protobuf는 열거 유형을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a3654-104">Protobuf supports enumeration types.</span></span> <span data-ttu-id="a3654-105">이전 섹션에서는 열거형이 `Oneof` 필드의 유형을 결정하는 데 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3654-105">You saw this support in the previous section, where an enum was used to determine the type of a `Oneof` field.</span></span> <span data-ttu-id="a3654-106">사용자 고유의 열거 형 유형을 정의할 수 있으며 Protobuf는 이를 C# 열거형 유형으로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="a3654-106">You can define your own enumeration types, and Protobuf will compile them to C# enum types.</span></span>

<span data-ttu-id="a3654-107">다양한 언어로 Protobuf를 사용할 수 있으므로 열거에 대한 명명 규칙은 C# 규칙과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a3654-107">Because you can use Protobuf with various languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="a3654-108">그러나 코드 생성기는 이름을 기존 C# 사례로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="a3654-108">However, the code generator converts the names to the traditional C# case.</span></span> <span data-ttu-id="a3654-109">필드 이름과 동일한 파스칼 대/소문자가 열거 형 이름으로 시작하면 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3654-109">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="a3654-110">예를 들어 다음 Protobuf 열거형에서 필드에 는 접두사입니다. `ACCOUNT_STATUS`</span><span class="sxs-lookup"><span data-stu-id="a3654-110">For example, in the following Protobuf enumeration, the fields are prefixed with `ACCOUNT_STATUS`.</span></span> <span data-ttu-id="a3654-111">이 접두사는 파스칼 대/소문자 열거형 이름과 동일합니다. `AccountStatus`</span><span class="sxs-lookup"><span data-stu-id="a3654-111">This prefix is equivalent to the Pascal-case enum name, `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="a3654-112">생성기는 다음 코드와 동일한 C# 열거형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a3654-112">The generator creates a C# enum equivalent to the following code:</span></span>

```csharp
public enum AccountStatus
{
    Unknown = 0,
    Pending = 1,
    Active = 2,
    Suspended = 3,
    Closed = 4
}
```

<span data-ttu-id="a3654-113">Protobuf 열거 정의는 첫 번째 필드로 0 상수가 *있어야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="a3654-113">Protobuf enumeration definitions *must* have a zero constant as their first field.</span></span> <span data-ttu-id="a3654-114">C#에서와 마찬가지로 동일한 값을 가진 여러 필드를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3654-114">As in C#, you can declare multiple fields with the same value.</span></span> <span data-ttu-id="a3654-115">그러나 열거형의 `allow_alias` 옵션을 사용하여 이 옵션을 명시적으로 활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3654-115">But you must explicitly enable this option by using the `allow_alias` option in the enum:</span></span>

```protobuf
enum AccountStatus {
  option allow_alias = true;
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
  ACCOUNT_STATUS_CANCELLED = 4;
}
```

<span data-ttu-id="a3654-116">`.proto` 파일의 최상위 수준에서 열거를 선언하거나 메시지 정의 내에 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3654-116">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="a3654-117">중첩된 메시지와 같은 중첩 열거형은 생성된 `.Types` 메시지 클래스의 정적 클래스 내에서 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3654-117">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="a3654-118">프로토부프가 생성한 열거형에 [[깃발]](xref:System.FlagsAttribute) 속성을 적용할 수 있는 방법은 없으며, Protobuf는 비트별 열거형 조합을 이해하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="a3654-118">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="a3654-119">다음 예제를 살펴보십시오.</span><span class="sxs-lookup"><span data-stu-id="a3654-119">Look at the following example:</span></span>

```protobuf
enum Region {
  REGION_NONE = 0;
  REGION_NORTH_AMERICA = 1;
  REGION_SOUTH_AMERICA = 2;
  REGION_EMEA = 4;
  REGION_APAC = 8;
}

message Product {
  Region available_in = 1;
}
```

<span data-ttu-id="a3654-120">을 로 `product.AvailableIn` 설정하면 정수 값으로 `3`직렬화됩니다. `Region.NorthAmerica | Region.SouthAmerica`</span><span class="sxs-lookup"><span data-stu-id="a3654-120">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="a3654-121">클라이언트 또는 서버가 값을 역직렬화하려고 하면 에 대한 `3`열거형 정의에서 일치하는 값을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3654-121">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3`.</span></span> <span data-ttu-id="a3654-122">결과는 . `Region.None`</span><span class="sxs-lookup"><span data-stu-id="a3654-122">The result will be `Region.None`.</span></span>

<span data-ttu-id="a3654-123">Protobuf에서 여러 열거형 값으로 작업하는 가장 `repeated` 좋은 방법은 열거형 형식의 필드를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a3654-123">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a3654-124">[이전](protobuf-any-oneof.md)
>[다음](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="a3654-124">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
