---
title: '호환성이 손상되는 변경: BinaryFormatter.Deserialize가 일부 예외를 다시 래핑함'
description: BinaryFormatter.Deserialize가 SerializationException 내에서 일부 예외 개체를 다시 래핑하는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 08/18/2020
ms.openlocfilehash: 90dc4cce6785fdb38644cca2a2e9aff65eb7a313
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759684"
---
# <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a><span data-ttu-id="39603-103">BinaryFormatter.Deserialize가 SerializationException에서 일부 예외를 다시 래핑</span><span class="sxs-lookup"><span data-stu-id="39603-103">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>

<span data-ttu-id="39603-104">이제 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> 메서드는 예외를 호출자에게 전파하기 전에 <xref:System.Runtime.Serialization.SerializationException> 내부에서 일부 예외 개체를 다시 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="39603-104">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method now rewraps some exception objects inside a <xref:System.Runtime.Serialization.SerializationException> before propagating the exception back to the caller.</span></span>

## <a name="change-description"></a><span data-ttu-id="39603-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="39603-105">Change description</span></span>

<span data-ttu-id="39603-106">이전에는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> 메서드가 <xref:System.ArgumentNullException> 같은 임의 예외에서 스택을 호출자에게 전파하도록 허용했습니다.</span><span class="sxs-lookup"><span data-stu-id="39603-106">Previously, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method allowed some arbitrary exceptions, such as <xref:System.ArgumentNullException>, to propagate up the stack to its callers.</span></span>

<span data-ttu-id="39603-107">.NET 5.0 이상에서 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> 메서드는 잘못된 deserialization 작업으로 인해 발생하는 예외를 더 적극적으로 catch하여 <xref:System.Runtime.Serialization.SerializationException>에 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="39603-107">In .NET 5.0 and later, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method more aggressively catches exceptions that occur due to invalid deserialization operations and wraps them in a <xref:System.Runtime.Serialization.SerializationException>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="39603-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="39603-108">Version introduced</span></span>

<span data-ttu-id="39603-109">5.0</span><span class="sxs-lookup"><span data-stu-id="39603-109">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="39603-110">권장 조치</span><span class="sxs-lookup"><span data-stu-id="39603-110">Recommended action</span></span>

<span data-ttu-id="39603-111">대부분의 경우 아무 작업도 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39603-111">In most cases, you don't need to take any action.</span></span> <span data-ttu-id="39603-112">그러나 호출 사이트가 throw되는 특정 예외에 종속된 경우 다음 예제와 같이 외부 <xref:System.Runtime.Serialization.SerializationException>에서 예외를 래핑 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39603-112">However, if your call site depends on a particular exception being thrown, you can unwrap the exception from the outer <xref:System.Runtime.Serialization.SerializationException>, as shown in the following example.</span></span>

```csharp
Stream inputStream = GetInputStream();
var formatter = new BinaryFormatter();

try
{
    object deserialized = formatter.Deserialize(inputStream);
}
catch (MyException myEx)
{
    // Handle 'myEx' here in case it was thrown directly.
}
catch (SerializationException serEx) when (serEx.InnerException is MyException myEx)
{
    // Handle 'myEx' here in case it was wrapped in SerializationException.
}
```

## <a name="affected-apis"></a><span data-ttu-id="39603-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="39603-113">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

### Category

Serialization

-->
