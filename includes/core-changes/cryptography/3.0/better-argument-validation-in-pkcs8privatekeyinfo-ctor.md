---
ms.openlocfilehash: a9b6af31b68c25ab58c52757f48ed23cca3f5a35
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567964"
---
### <a name="better-argument-validation-in-the-pkcs8privatekeyinfo-constructor"></a><span data-ttu-id="a440b-101">Pkcs8PrivateKeyInfo 생성자의 인수 유효성 검사를 개선</span><span class="sxs-lookup"><span data-stu-id="a440b-101">Better argument validation in the Pkcs8PrivateKeyInfo constructor</span></span>

<span data-ttu-id="a440b-102">.Net Core 3.0 미리 보기 9부터 `Pkcs8PrivateKeyInfo` 생성자는 `algorithmParameters` 매개 변수의 유효성을 BER 인코딩된 단일 값으로 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="a440b-102">Starting with .NET Core 3.0 Preview 9, the `Pkcs8PrivateKeyInfo` constructor validates the `algorithmParameters` parameter as a single BER-encoded value.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a440b-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="a440b-103">Change description</span></span>

<span data-ttu-id="a440b-104">.Net Core 3.0 미리 보기 9 이전에는 [`Pkcs8PrivateKeyInfo` 생성자](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))가 `algorithmParameters`인수의 유효성을 검사하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a440b-104">Before .NET Core 3.0 Preview 9, the [`Pkcs8PrivateKeyInfo` constructor](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean)) did not validate the `algorithmParameters` argument.</span></span>  <span data-ttu-id="a440b-105">이 인수가 잘못된 값을 나타내는 경우 생성자는 성공하지만 <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncode%2A>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encrypt%2A> 또는 <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncrypt%2A> 메서드를 호출할 경우 허용되지 않은 인수(`preEncodedValue`)에 대한 <xref:System.ArgumentException> 또는 <xref:System.Security.Cryptography.CryptographicException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="a440b-105">When this argument represented an invalid value, the constructor would succeed, but a call to any of the <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncode%2A>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encrypt%2A>, or <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncrypt%2A> methods would throw either an <xref:System.ArgumentException> for an argument they did not accept (`preEncodedValue`) or a <xref:System.Security.Cryptography.CryptographicException>.</span></span>

<span data-ttu-id="a440b-106">미리 보기 9 이전의 .NET Core 3.0을 사용하여 실행하는 경우 <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode> 메서드를 호출하는 경우에만 다음 코드에서 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="a440b-106">If run with .NET Core 3.0 before Preview 9, the following code throws an exception only when the <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode> method is called:</span></span>

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
// This line throws an ArgumentException for `preEncodedValue`:
byte[] encoded = info.Encode();
```

<span data-ttu-id="a440b-107">.NET Core 3.0 미리 보기 9부터 생성자가 인수의 유효성을 검사하여 값이 잘못된 경우 메서드가 <xref:System.Security.Cryptography.CryptographicException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="a440b-107">Starting with .NET Core 3.0 Preview 9, the argument is validated in the constructor, and an invalid value results in the method throwing a <xref:System.Security.Cryptography.CryptographicException>.</span></span> <span data-ttu-id="a440b-108">이 변경으로 인해 예외는 데이터 오류 소스에 보다 가까워집니다.</span><span class="sxs-lookup"><span data-stu-id="a440b-108">This change moves the exception closer to the source of the data error.</span></span> <span data-ttu-id="a440b-109">예:</span><span class="sxs-lookup"><span data-stu-id="a440b-109">For example:</span></span>

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

// This line throws a CryptographicException
var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
```

#### <a name="version-introduced"></a><span data-ttu-id="a440b-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="a440b-110">Version introduced</span></span>

<span data-ttu-id="a440b-111">3.0 미리 보기 9</span><span class="sxs-lookup"><span data-stu-id="a440b-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a440b-112">권장 작업</span><span class="sxs-lookup"><span data-stu-id="a440b-112">Recommended action</span></span>

<span data-ttu-id="a440b-113">유효한 `algorithmParameters` 값만 제공하고 예외 처리가 필요한 경우 <xref:System.ArgumentException> 및 <xref:System.Security.Cryptography.CryptographicException> 모두에 대해 `Pkcs8PrivateKeyInfo` 생성자 테스트가 호출되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a440b-113">Ensure that only valid `algorithmParameters` values are provided, or that calls to the `Pkcs8PrivateKeyInfo` constructor test for both <xref:System.ArgumentException> and <xref:System.Security.Cryptography.CryptographicException> if exception handling is desired.</span></span>

### <a name="category"></a><span data-ttu-id="a440b-114">범주</span><span class="sxs-lookup"><span data-stu-id="a440b-114">Category</span></span>

<span data-ttu-id="a440b-115">암호화</span><span class="sxs-lookup"><span data-stu-id="a440b-115">Cryptography</span></span>

### <a name="affected-apis"></a><span data-ttu-id="a440b-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a440b-116">Affected APIs</span></span>

- <span data-ttu-id="a440b-117">[Pkcs8PrivateKeyInfo 생성자](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))</span><span class="sxs-lookup"><span data-stu-id="a440b-117">[Pkcs8PrivateKeyInfo constructor](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))</span></span>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.#ctor(System.Security.Cryptography.Oid,System.Nullable{System.ReadOnlyMemory{System.Byte}},System.ReadOnlyMemory{System.Byte},System.Boolean))

-->
