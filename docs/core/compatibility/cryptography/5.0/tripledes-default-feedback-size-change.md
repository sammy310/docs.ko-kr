---
title: '호환성이 손상되는 변경: TripleDES.Create에서 생성된 인스턴스의 기본 FeedbackSize 값이 변경됨'
description: TripleDES.Create()에서 반환된 TripleDES 인스턴스의 FeedbackSize 속성에 대한 기본값이 64에서 8로 변경된 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 10/16/2020
ms.openlocfilehash: 9d3259da30cce84e83a3f13c610dad5884b445b8
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256766"
---
# <a name="default-feedbacksize-value-for-instances-created-by-tripledescreate-changed"></a>TripleDES.Create에서 생성된 인스턴스의 기본 FeedbackSize 값이 변경됨

<xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType>에서 반환된 <xref:System.Security.Cryptography.TripleDES> 인스턴스에서 <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=nameWithType> 속성의 기본값은 .NET Framework에서 더 쉽게 마이그레이션할 수 있도록 64에서 8로 변경되었습니다. 호출자 코드에서 직접 사용되지 않는 경우 이 속성은 <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> 속성이 <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>인 경우에만 사용됩니다.

<xref:System.Security.Cryptography.CipherMode.CFB> 모드 지원은 5.0 RC1 릴리스의 .NET에 처음 추가되었으므로 .NET 5 RC1 및 .NET 5 RC2 애플리케이션만 해당 변경의 영향을 받습니다.

## <a name="change-description"></a>변경 내용 설명

.NET Core 및 이전 .NET 5 시험판 버전에서 `TripleDES.Create().FeedbackSize`의 기본값은 64입니다. RTM 버전의 .NET 5부터 `TripleDES.Create().FeedbackSize`의 기본값은 8입니다.

## <a name="reason-for-change"></a>변경 이유

.NET Framework에서 <xref:System.Security.Cryptography.TripleDES> 기본 클래스는 <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> 값을 기본적으로 64로 설정하지만 <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> 클래스는 기본값을 8로 덮어씁니다. <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> 속성이 버전 2.0의 .NET Core에 도입될 때 동일한 동작이 유지되었습니다. 그러나 .NET Framework에서 <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType>은 <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>의 인스턴스를 반환하므로 알고리즘 팩터리의 기본값은 8입니다. .NET Core 및 .NET 5 이상의 경우 알고리즘 팩터리는 지금까지 기본값이 64였던 퍼블릭이 아닌 구현을 반환합니다.

<xref:System.Security.Cryptography.TripleDES> 구현 클래스의 <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> 값을 8로 변경하면 암호화 모드를 <xref:System.Security.Cryptography.CipherMode.CFB>로 지정하지만 <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> 속성을 명시적으로 할당하지 않은 .NET Framework용으로 작성된 애플리케이션이 .NET 5에서 계속 작동할 수 있습니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

다음 조건이 충족되면 RC1 또는 RC2 버전의 .NET 5에서 데이터를 암호화하거나 암호 해독하는 애플리케이션은 CFB64를 사용하여 해당 작업을 수행합니다.

- <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType>의 <xref:System.Security.Cryptography.TripleDES> 인스턴스 포함.
- <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>의 기본값 사용.
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> 속성이 <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>로 설정됨.

이 동작을 유지 관리하려면 `64`에 <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> 속성을 할당합니다.

일부 `TripleDES` 구현은 <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>에 대해 동일한 기본값을 사용하지 않습니다. <xref:System.Security.Cryptography.TripleDES> 인스턴스에서 <xref:System.Security.Cryptography.CipherMode.CFB> 암호화 모드를 사용하는 경우 항상 <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> 속성 값을 명시적으로 할당하는 것이 좋습니다.

```csharp
TripleDES cipher = TripleDES.Create();
cipher.Mode = CipherMode.CFB;
// Explicitly set the FeedbackSize for CFB to control between CFB8 and CFB64.
cipher.FeedbackSize = 8;
```

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Security.Cryptography.TripleDES.Create`
- `P:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize`

### Category

- Cryptography

-->
