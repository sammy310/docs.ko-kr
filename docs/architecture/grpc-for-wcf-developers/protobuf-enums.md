---
title: Protobuf 열거형-WCF 개발자를 위한 gRPC
description: Protobuf에서 열거형을 선언 하 고 사용 하는 방법에 대해 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: 01cf4a4e5e0eda1e7ddff2a6780119fcb3120dad
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543146"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="bd97c-103">Protobuf 열거형</span><span class="sxs-lookup"><span data-stu-id="bd97c-103">Protobuf enumerations</span></span>

<span data-ttu-id="bd97c-104">Protobuf는 열거형 형식을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-104">Protobuf supports enumeration types.</span></span> <span data-ttu-id="bd97c-105">열거형이 `Oneof` 필드의 형식을 결정 하는 데 사용 된 이전 섹션에서이 지원을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-105">You saw this support in the previous section, where an enum was used to determine the type of a `Oneof` field.</span></span> <span data-ttu-id="bd97c-106">사용자 고유의 열거형 형식을 정의할 수 있으며, Protobuf는 열거형 형식으로 C# 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-106">You can define your own enumeration types, and Protobuf will compile them to C# enum types.</span></span> 

<span data-ttu-id="bd97c-107">다양 한 언어와 함께 Protobuf를 사용할 수 있으므로 열거의 명명 규칙은 C# 규칙과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-107">Because you can use Protobuf with various languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="bd97c-108">그러나 코드 생성기는 이름을 기존 C# case로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-108">However, the code generator converts the names to the traditional C# case.</span></span> <span data-ttu-id="bd97c-109">필드 이름에 해당 하는 파스칼식 대/소문자가 열거형 이름으로 시작 하는 경우 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-109">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="bd97c-110">예를 들어 다음 Protobuf 열거형에서 필드에는 `ACCOUNT_STATUS`접두사가 붙습니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-110">For example, in the following Protobuf enumeration, the fields are prefixed with `ACCOUNT_STATUS`.</span></span> <span data-ttu-id="bd97c-111">이 접두사는 파스칼식 대/소문자 열거형 이름 `AccountStatus`와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-111">This prefix is equivalent to the Pascal-case enum name, `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="bd97c-112">생성기는 다음 코드 C# 에 해당 하는 열거형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-112">The generator creates a C# enum equivalent to the following code:</span></span>

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

<span data-ttu-id="bd97c-113">Protobuf 열거형 정의에는 첫 번째 필드로 0 상수가 *있어야* 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-113">Protobuf enumeration definitions *must* have a zero constant as their first field.</span></span> <span data-ttu-id="bd97c-114">에서 C#와 같이 같은 값을 사용 하 여 여러 필드를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-114">As in C#, you can declare multiple fields with the same value.</span></span> <span data-ttu-id="bd97c-115">그러나 열거형에서 `allow_alias` 옵션을 사용 하 여이 옵션을 명시적으로 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-115">But you must explicitly enable this option by using the `allow_alias` option in the enum:</span></span>

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

<span data-ttu-id="bd97c-116">`.proto` 파일의 최상위 수준에서 열거형을 선언 하거나 메시지 정의 내에 중첩 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-116">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="bd97c-117">중첩 된 메시지와 같이 중첩 된 열거형은 생성 된 메시지 클래스의 `.Types` 정적 클래스 내에서 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-117">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="bd97c-118">Protobuf에서 생성 된 열거형에는 [[Flags]](xref:System.FlagsAttribute) 특성을 적용할 수 없으며 Protobuf는 비트 열거형 조합을 인식 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-118">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="bd97c-119">다음 예제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-119">Look at the following example:</span></span>

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

<span data-ttu-id="bd97c-120">`product.AvailableIn`을 `Region.NorthAmerica | Region.SouthAmerica`로 설정 하면 `3`정수 값으로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-120">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="bd97c-121">클라이언트 또는 서버에서 값을 deserialize 하려고 하면 `3`의 열거 정의에서 일치 항목을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-121">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3`.</span></span> <span data-ttu-id="bd97c-122">결과는 `Region.None`됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-122">The result will be `Region.None`.</span></span>

<span data-ttu-id="bd97c-123">Protobuf에서 여러 열거형 값으로 작업 하는 가장 좋은 방법은 열거형 형식의 `repeated` 필드를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bd97c-123">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bd97c-124">[이전](protobuf-any-oneof.md)
>[다음](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="bd97c-124">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
