---
ms.openlocfilehash: abcab63b5a90a70cc9dfabb031e94ce379e5471b
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720203"
---
### <a name="parameter-names-changed-in-reference-assemblies"></a><span data-ttu-id="13a20-101">참조 어셈블리의 매개 변수 이름 변경됨</span><span class="sxs-lookup"><span data-stu-id="13a20-101">Parameter names changed in reference assemblies</span></span>

<span data-ttu-id="13a20-102">참조 어셈블리의 일부 매개 변수 이름이 구현 어셈블리의 매개 변수 이름과 일치하도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="13a20-102">Some reference assembly parameter names have changed to match parameter names in the implementation assemblies.</span></span>

#### <a name="change-description"></a><span data-ttu-id="13a20-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="13a20-103">Change description</span></span>

<span data-ttu-id="13a20-104">이전 .NET 버전에서는 [참조 어셈블리](../../../../docs/standard/assembly/reference-assemblies.md)의 일부 매개 변수 이름이 구현 어셈블리의 해당 매개 변수와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="13a20-104">In previous .NET versions, some [reference assembly](../../../../docs/standard/assembly/reference-assemblies.md) parameter names are different to their corresponding parameters in the implementation assembly.</span></span> <span data-ttu-id="13a20-105">이로 인해 명명된 인수와 리플렉션을 사용하는 동안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13a20-105">This can cause problems while using named arguments and reflection.</span></span>

<span data-ttu-id="13a20-106">.NET 5.0에서는 참조 어셈블리의 일치하지 않는 매개 변수 이름이 구현 어셈블리의 해당 매개 변수 이름과 정확히 일치하도록 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="13a20-106">In .NET 5.0, these mismatched parameter names were updated in the reference assemblies to exactly match the corresponding parameter names in the implementation assemblies.</span></span>

<span data-ttu-id="13a20-107">다음 표에는 변경된 API 및 매개 변수 이름이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13a20-107">The following table shows the APIs and parameter names that changed.</span></span>

| <span data-ttu-id="13a20-108">API</span><span class="sxs-lookup"><span data-stu-id="13a20-108">API</span></span> | <span data-ttu-id="13a20-109">이전 매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="13a20-109">Old parameter name</span></span> | <span data-ttu-id="13a20-110">새 매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="13a20-110">New parameter name</span></span> |
| - | - | - |
| <xref:System.CodeDom.Compiler.CodeGenerator.GenerateStatements(System.CodeDom.CodeStatementCollection)?displayProperty=nameWithType> | `stms` | `stmts` |
| <xref:System.Drawing.Icon.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | `si` |
| <xref:System.Drawing.Image.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | `si` |
| <xref:System.Net.IPAddress.Parse(System.ReadOnlySpan{System.Char})?displayProperty=nameWithType> | `ipString` | `ipSpan` |
| <xref:System.Net.IPAddress.TryParse(System.ReadOnlySpan{System.Char},System.Net.IPAddress@)?displayProperty=nameWithType> | `ipString` | `ipSpan` |
| <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=nameWithType> | `buffer` | `array` |
| <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=nameWithType> | `buffer` | `array` |
| <xref:System.Net.NetworkCredential.GetCredential(System.String,System.Int32,System.String)?displayProperty=nameWithType> | `authType` | `authenticationType` |
| <xref:System.ComponentModel.ParenthesizePropertyNameAttribute.Equals(System.Object)?displayProperty=nameWithType> | `o` | `obj` |
| <xref:System.ComponentModel.RefreshPropertiesAttribute.Equals(System.Object)?displayProperty=nameWithType> | `value` | `obj` |
| <xref:System.Diagnostics.StackFrame.%23ctor(System.Boolean)> | `fNeedFileInfo` | `needFileInfo` |
| <xref:System.Diagnostics.StackFrame.%23ctor(System.Int32,System.Boolean)> | `fNeedFileInfo` | `needFileInfo` |
| <xref:System.StringNormalizationExtensions.IsNormalized(System.String,System.Text.NormalizationForm)?displayProperty=nameWithType> | `value` | `strInput` |
| <xref:System.StringNormalizationExtensions.IsNormalized(System.String)?displayProperty=nameWithType> | `value` | `strInput` |
| <xref:System.StringNormalizationExtensions.Normalize(System.String,System.Text.NormalizationForm)?displayProperty=nameWithType> | `value` | `strInput` |
| <xref:System.StringNormalizationExtensions.Normalize(System.String)?displayProperty=nameWithType> | `value` | `strInput` |

#### <a name="reason-for-change"></a><span data-ttu-id="13a20-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="13a20-111">Reason for change</span></span>

<span data-ttu-id="13a20-112">일관성을 유지하고 명명된 인수와 리플렉션을 사용할 때 오류를 방지하기 위해 매개 변수 이름이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="13a20-112">The parameter names were changed for consistency and to avoid failures when using named arguments and reflection.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="13a20-113">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="13a20-113">Version introduced</span></span>

<span data-ttu-id="13a20-114">5.0</span><span class="sxs-lookup"><span data-stu-id="13a20-114">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="13a20-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="13a20-115">Recommended action</span></span>

<span data-ttu-id="13a20-116">매개 변수 이름 변경으로 인해 컴파일러 오류가 발생하는 경우 매개 변수 이름을 적절하게 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="13a20-116">If you encounter a compiler error due to a parameter name change, update the parameter name accordingly.</span></span>

#### <a name="category"></a><span data-ttu-id="13a20-117">범주</span><span class="sxs-lookup"><span data-stu-id="13a20-117">Category</span></span>

<span data-ttu-id="13a20-118">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="13a20-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="13a20-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="13a20-119">Affected APIs</span></span>

- <xref:System.CodeDom.Compiler.CodeGenerator.GenerateStatements(System.CodeDom.CodeStatementCollection)?displayProperty=fullName>
- <xref:System.ComponentModel.ParenthesizePropertyNameAttribute.Equals(System.Object)?displayProperty=fullName>
- <xref:System.ComponentModel.RefreshPropertiesAttribute.Equals(System.Object)?displayProperty=fullName>
- <xref:System.Diagnostics.StackFrame.%23ctor(System.Boolean)>
- <xref:System.Diagnostics.StackFrame.%23ctor(System.Int32,System.Boolean)>
- <xref:System.Drawing.Icon.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=fullName>
- <xref:System.Drawing.Image.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=fullName>
- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.Net.IPAddress.Parse(System.ReadOnlySpan{System.Char})?displayProperty=fullName>
- <xref:System.Net.IPAddress.TryParse(System.ReadOnlySpan{System.Char},System.Net.IPAddress@)?displayProperty=fullName>
- <xref:System.Net.NetworkCredential.GetCredential(System.String,System.Int32,System.String)?displayProperty=fullName>
- <xref:System.StringNormalizationExtensions.IsNormalized(System.String,System.Text.NormalizationForm)?displayProperty=fullName>
- <xref:System.StringNormalizationExtensions.IsNormalized(System.String)?displayProperty=fullName>
- <xref:System.StringNormalizationExtensions.Normalize(System.String,System.Text.NormalizationForm)?displayProperty=fullName>
- <xref:System.StringNormalizationExtensions.Normalize(System.String)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.CodeDom.Compiler.CodeGenerator.GenerateStatements(System.CodeDom.CodeStatementCollection)`
- `M:System.Diagnostics.StackFrame.#ctor(System.Boolean)`
- `M:System.Diagnostics.StackFrame.#ctor(System.Int32,System.Boolean)`
- `M:System.Net.NetworkCredential.GetCredential(System.String,System.Int32,System.String)`
- `M:System.Net.IPAddress.Parse(System.ReadOnlySpan{System.Char})`
- `M:System.Net.IPAddress.TryParse(System.ReadOnlySpan{System.Char},System.Net.IPAddress@)`
- `M:System.StringNormalizationExtensions.IsNormalized(System.String,System.Text.NormalizationForm)`
- `M:System.StringNormalizationExtensions.IsNormalized(System.String)`
- `M:System.StringNormalizationExtensions.Normalize(System.String,System.Text.NormalizationForm)`
- `M:System.StringNormalizationExtensions.Normalize(System.String)`
- `M:System.IO.IsolatedStorage.IsolatedStorageFileStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.IsolatedStorage.IsolatedStorageFileStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.ComponentModel.ParenthesizePropertyNameAttribute.Equals(System.Object)`
- `M:System.ComponentModel.RefreshPropertiesAttribute.Equals(System.Object)`
- `M:System.Drawing.Icon.System#Runtime#Serialization#ISerializable#GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)`
- `M:System.Drawing.Image.System#Runtime#Serialization#ISerializable#GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)`

-->
