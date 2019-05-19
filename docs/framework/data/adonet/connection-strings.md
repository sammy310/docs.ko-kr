---
title: ADO.NET의 연결 문자열
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 3b7cb0ab061da8364a9fecc3868ba9aaf7501577
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881155"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="0d690-102">ADO.NET의 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="0d690-102">Connection Strings in ADO.NET</span></span>

<span data-ttu-id="0d690-103">연결 문자열에는 데이터 공급자에서 데이터 소스에 매개 변수로 전달되는 초기화 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-103">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="0d690-104">값으로 연결 문자열을 수신 하는 데이터 공급자는 <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-104">The data provider receives the connection string as the value of the <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="0d690-105">공급자 연결 문자열을 구문 분석 및 구문이 올바르고 키워드를 지원 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-105">The provider parses the connection string and ensures that the syntax is correct and that the keywords are supported.</span></span> <span data-ttu-id="0d690-106">그런 다음 <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> 메서드는 데이터 원본에 구문 분석 된 연결 매개 변수를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-106">Then the <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> method passes the parsed connection parameters to the data source.</span></span> <span data-ttu-id="0d690-107">데이터 원본 추가 유효성 검사를 수행 하 고 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-107">The data source performs further validation and establishes a connection.</span></span>

## <a name="connection-string-syntax"></a><span data-ttu-id="0d690-108">연결 문자열 구문</span><span class="sxs-lookup"><span data-stu-id="0d690-108">Connection string syntax</span></span>

<span data-ttu-id="0d690-109">연결 문자열은 키/값 매개 변수 쌍의 세미콜론으로 구분 된 목록:</span><span class="sxs-lookup"><span data-stu-id="0d690-109">A connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>

```
keyword1=value; keyword2=value;
```

<span data-ttu-id="0d690-110">키워드는 대/소문자 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-110">Keywords are not case-sensitive.</span></span> <span data-ttu-id="0d690-111">그러나 값을 않을 대/소문자 구분, 데이터 원본에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-111">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="0d690-112">키워드와 값이 포함 될 수 있습니다 [공백 문자](https://en.wikipedia.org/wiki/Whitespace_character#Unicode)합니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-112">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span></span> <span data-ttu-id="0d690-113">선행 및 후행 공백을 키워드에서 무시 되 고 따옴표가 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-113">Leading and trailing white space is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="0d690-114">값을 세미콜론을 포함 하는 경우 [유니코드 제어 문자](https://en.wikipedia.org/wiki/Unicode_control_characters), 또는 단일 또는 이중 따옴표로 묶어야 합니다 선행 또는 후행 공백을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-114">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), or leading or trailing white space, it must be enclosed in single or double quotation marks.</span></span> <span data-ttu-id="0d690-115">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="0d690-115">For example:</span></span>

```
Keyword=" whitespace  ";
Keyword='special;character';
```

<span data-ttu-id="0d690-116">바깥쪽 문자 값이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-116">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="0d690-117">따라서 큰따옴표에만 그 반대로 작은따옴표를 포함 하는 값을 묶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-117">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks, and vice versa:</span></span>

```
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

<span data-ttu-id="0d690-118">등호 기호 뿐만 아니라 자체에 따옴표 필요 하지 않습니다, 이스케이프 다음 연결 문자열을 유효한 되므로:</span><span class="sxs-lookup"><span data-stu-id="0d690-118">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

```
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

<span data-ttu-id="0d690-119">두 번째 예의 값은 각 값은 다음 세미콜론 이나 문자열의 끝까지 내용은 이후 `a=b=c`, 최종 세미콜론 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-119">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="0d690-120">모든 연결 문자열에는 위에서 설명한 동일한 기본 구문을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-120">All connection strings share the same basic syntax described above.</span></span> <span data-ttu-id="0d690-121">그러나 공급자에 따라 달라 집니다 및와 같은 초기 Api 에서부터 수 년에 걸쳐 발전해 인식 된 키워드 집합 *ODBC*합니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-121">The set of recognized keywords depends on the provider, however, and has evolved over the years from earlier APIs such as *ODBC*.</span></span> <span data-ttu-id="0d690-122">합니다 *.NET Framework* 에 대 한 데이터 공급자 *SQL Server* (`SqlClient`) 이전 Api에서 여러 키워드를 지원 하지만 일반적으로 더 유연 하 고 다양 한 일반적인 연결 문자열에 대 한 동의어를 허용 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-122">The *.NET Framework* data provider for *SQL Server* (`SqlClient`) supports many keywords from older APIs, but is generally more flexible and accepts synonyms for many of the common connection string keywords.</span></span>

<span data-ttu-id="0d690-123">실수를 입력 하면 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-123">Typing mistakes can cause errors.</span></span> <span data-ttu-id="0d690-124">예를 들어 `Integrated Security=true` 유효 하지만 `IntegratedSecurity=true` 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-124">For example, `Integrated Security=true` is valid, but `IntegratedSecurity=true` causes an error.</span></span>

<span data-ttu-id="0d690-125">런타임에 유효성이 검사 되지 않은 사용자 입력에서 수동으로 구성 된 연결 문자열은 문자열 삽입 공격에 취약 및 데이터 소스에서 보안을 위협할 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-125">Connection strings constructed manually at run time from unvalidated user input are vulnerable to string-injection attacks and jeopardize security at the data source.</span></span> <span data-ttu-id="0d690-126">이러한 문제를 해결 하기 위해 *ADO.NET* 2.0에서는 [연결 문자열 작성기](../../../../docs/framework/data/adonet/connection-string-builders.md) 마다 *.NET Framework* 데이터 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-126">To address these problems, *ADO.NET* 2.0 introduced [connection string builders](../../../../docs/framework/data/adonet/connection-string-builders.md) for each *.NET Framework* data provider.</span></span> <span data-ttu-id="0d690-127">이러한 연결 문자열 작성기 매개 변수를 강력한 형식의 속성을 노출 하 고 연결 문자열을 데이터 원본에 전송 되기 전에 유효성을 검사할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-127">These connection string builders expose parameters as strongly-typed properties, and make it possible to validate the connection string before it's sent to the data source.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0d690-128">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="0d690-128">In This Section</span></span>

<span data-ttu-id="0d690-129">[연결 문자열 작성기](../../../../docs/framework/data/adonet/connection-string-builders.md)\\</span><span class="sxs-lookup"><span data-stu-id="0d690-129">[Connection String Builders](../../../../docs/framework/data/adonet/connection-string-builders.md)\\</span></span>
<span data-ttu-id="0d690-130">`ConnectionStringBuilder` 클래스를 사용하여 런타임에 유효한 연결 문자열을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-130">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>

<span data-ttu-id="0d690-131">[연결 문자열 및 구성 파일](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)\\</span><span class="sxs-lookup"><span data-stu-id="0d690-131">[Connection Strings and Configuration Files](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)\\</span></span>
<span data-ttu-id="0d690-132">구성 파일에서 연결 문자열을 저장하고 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-132">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>

<span data-ttu-id="0d690-133">[연결 문자열 구문](../../../../docs/framework/data/adonet/connection-string-syntax.md)\\</span><span class="sxs-lookup"><span data-stu-id="0d690-133">[Connection String Syntax](../../../../docs/framework/data/adonet/connection-string-syntax.md)\\</span></span>
<span data-ttu-id="0d690-134">`SqlClient`, `OracleClient`, `OleDb` 및 `Odbc`에 대한 공급자별 연결 문자열을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-134">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>

<span data-ttu-id="0d690-135">[연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)\\</span><span class="sxs-lookup"><span data-stu-id="0d690-135">[Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md)\\</span></span>
<span data-ttu-id="0d690-136">데이터 소스 연결에 사용되는 정보를 보호하는 기법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d690-136">Demonstrates techniques for protecting information used to connect to a data source.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d690-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="0d690-137">See also</span></span>

- [<span data-ttu-id="0d690-138">데이터 소스에 연결</span><span class="sxs-lookup"><span data-stu-id="0d690-138">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)
- [<span data-ttu-id="0d690-139">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="0d690-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
