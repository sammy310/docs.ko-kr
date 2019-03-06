---
title: ODBC 스키마 컬렉션
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ffe80120ceffbe29c0a117cf1194860c5782be8c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365908"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="907b6-102">ODBC 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="907b6-102">ODBC Schema Collections</span></span>

<span data-ttu-id="907b6-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 ODBC 드라이버에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="907b6-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="907b6-104">Microsoft SQL Server ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="907b6-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="907b6-105">Microsoft SQL Server ODBC Driver에서는 공통 스키마 컬렉션 외에도 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="907b6-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="907b6-106">Tables</span><span class="sxs-lookup"><span data-stu-id="907b6-106">Tables</span></span>

- <span data-ttu-id="907b6-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="907b6-107">Indexes</span></span>

- <span data-ttu-id="907b6-108">Columns</span><span class="sxs-lookup"><span data-stu-id="907b6-108">Columns</span></span>

- <span data-ttu-id="907b6-109">절차</span><span class="sxs-lookup"><span data-stu-id="907b6-109">Procedures</span></span>

- <span data-ttu-id="907b6-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="907b6-110">ProcedureColumns</span></span>

- <span data-ttu-id="907b6-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="907b6-111">ProcedureParameters</span></span>

- <span data-ttu-id="907b6-112">뷰</span><span class="sxs-lookup"><span data-stu-id="907b6-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="907b6-113">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="907b6-113">Tables and Views</span></span>

|<span data-ttu-id="907b6-114">열 이름</span><span class="sxs-lookup"><span data-stu-id="907b6-114">ColumnName</span></span>|<span data-ttu-id="907b6-115">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="907b6-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="907b6-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="907b6-116">TABLE_CAT</span></span>|<span data-ttu-id="907b6-117">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-117">String</span></span>|
|<span data-ttu-id="907b6-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="907b6-118">TABLE_SCHEM</span></span>|<span data-ttu-id="907b6-119">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-119">String</span></span>|
|<span data-ttu-id="907b6-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-120">TABLE_NAME</span></span>|<span data-ttu-id="907b6-121">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-121">String</span></span>|
|<span data-ttu-id="907b6-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-122">TABLE_TYPE</span></span>|<span data-ttu-id="907b6-123">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-123">String</span></span>|
|<span data-ttu-id="907b6-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="907b6-124">REMARKS</span></span>|<span data-ttu-id="907b6-125">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="907b6-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="907b6-126">Indexes</span></span>

|<span data-ttu-id="907b6-127">열 이름</span><span class="sxs-lookup"><span data-stu-id="907b6-127">ColumnName</span></span>|<span data-ttu-id="907b6-128">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="907b6-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="907b6-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="907b6-129">TABLE_CAT</span></span>|<span data-ttu-id="907b6-130">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-130">String</span></span>|
|<span data-ttu-id="907b6-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="907b6-131">TABLE_SCHEM</span></span>|<span data-ttu-id="907b6-132">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-132">String</span></span>|
|<span data-ttu-id="907b6-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-133">TABLE_NAME</span></span>|<span data-ttu-id="907b6-134">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-134">String</span></span>|
|<span data-ttu-id="907b6-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="907b6-135">NON_UNIQUE</span></span>|<span data-ttu-id="907b6-136">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-136">Int16</span></span>|
|<span data-ttu-id="907b6-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="907b6-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="907b6-138">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-138">String</span></span>|
|<span data-ttu-id="907b6-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-139">INDEX_NAME</span></span>|<span data-ttu-id="907b6-140">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-140">String</span></span>|
|<span data-ttu-id="907b6-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-141">TYPE</span></span>|<span data-ttu-id="907b6-142">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-142">Int16</span></span>|
|<span data-ttu-id="907b6-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="907b6-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="907b6-144">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-144">Int16</span></span>|
|<span data-ttu-id="907b6-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-145">COLUMN_NAME</span></span>|<span data-ttu-id="907b6-146">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-146">String</span></span>|
|<span data-ttu-id="907b6-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="907b6-147">ASC_OR_DESC</span></span>|<span data-ttu-id="907b6-148">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-148">String</span></span>|
|<span data-ttu-id="907b6-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="907b6-149">CARDINALITY</span></span>|<span data-ttu-id="907b6-150">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-150">Int32</span></span>|
|<span data-ttu-id="907b6-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="907b6-151">PAGES</span></span>|<span data-ttu-id="907b6-152">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-152">Int32</span></span>|
|<span data-ttu-id="907b6-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="907b6-153">FILTER_CONDITION</span></span>|<span data-ttu-id="907b6-154">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-154">String</span></span>|
|<span data-ttu-id="907b6-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="907b6-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="907b6-156">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-156">String</span></span>|
|<span data-ttu-id="907b6-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="907b6-158">Byte</span><span class="sxs-lookup"><span data-stu-id="907b6-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="907b6-159">Columns</span><span class="sxs-lookup"><span data-stu-id="907b6-159">Columns</span></span>

|<span data-ttu-id="907b6-160">열 이름</span><span class="sxs-lookup"><span data-stu-id="907b6-160">ColumnName</span></span>|<span data-ttu-id="907b6-161">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="907b6-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="907b6-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="907b6-162">TABLE_CAT</span></span>|<span data-ttu-id="907b6-163">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-163">String</span></span>|
|<span data-ttu-id="907b6-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="907b6-164">TABLE_SCHEM</span></span>|<span data-ttu-id="907b6-165">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-165">String</span></span>|
|<span data-ttu-id="907b6-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-166">TABLE_NAME</span></span>|<span data-ttu-id="907b6-167">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-167">String</span></span>|
|<span data-ttu-id="907b6-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-168">COLUMN_NAME</span></span>|<span data-ttu-id="907b6-169">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-169">String</span></span>|
|<span data-ttu-id="907b6-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-170">DATA_TYPE</span></span>|<span data-ttu-id="907b6-171">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-171">Int16</span></span>|
|<span data-ttu-id="907b6-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-172">TYPE_NAME</span></span>|<span data-ttu-id="907b6-173">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-173">String</span></span>|
|<span data-ttu-id="907b6-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="907b6-174">COLUMN_SIZE</span></span>|<span data-ttu-id="907b6-175">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-175">Int32</span></span>|
|<span data-ttu-id="907b6-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="907b6-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="907b6-177">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-177">Int32</span></span>|
|<span data-ttu-id="907b6-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="907b6-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="907b6-179">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-179">Int16</span></span>|
|<span data-ttu-id="907b6-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="907b6-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="907b6-181">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-181">Int16</span></span>|
|<span data-ttu-id="907b6-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="907b6-182">NULLABLE</span></span>|<span data-ttu-id="907b6-183">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-183">Int16</span></span>|
|<span data-ttu-id="907b6-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="907b6-184">REMARKS</span></span>|<span data-ttu-id="907b6-185">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-185">String</span></span>|
|<span data-ttu-id="907b6-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="907b6-186">COLUMN_DEF</span></span>|<span data-ttu-id="907b6-187">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-187">String</span></span>|
|<span data-ttu-id="907b6-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="907b6-189">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-189">Int16</span></span>|
|<span data-ttu-id="907b6-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="907b6-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="907b6-191">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-191">Int16</span></span>|
|<span data-ttu-id="907b6-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="907b6-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="907b6-193">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-193">Int32</span></span>|
|<span data-ttu-id="907b6-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="907b6-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="907b6-195">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-195">Int32</span></span>|
|<span data-ttu-id="907b6-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="907b6-196">IS_NULLABLE</span></span>|<span data-ttu-id="907b6-197">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-197">String</span></span>|
|<span data-ttu-id="907b6-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="907b6-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="907b6-199">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-199">String</span></span>|
|<span data-ttu-id="907b6-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="907b6-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="907b6-201">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-201">String</span></span>|
|<span data-ttu-id="907b6-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="907b6-203">Byte</span><span class="sxs-lookup"><span data-stu-id="907b6-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="907b6-204">절차</span><span class="sxs-lookup"><span data-stu-id="907b6-204">Procedures</span></span>

|<span data-ttu-id="907b6-205">열 이름</span><span class="sxs-lookup"><span data-stu-id="907b6-205">ColumnName</span></span>|<span data-ttu-id="907b6-206">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="907b6-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="907b6-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="907b6-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="907b6-208">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-208">String</span></span>|
|<span data-ttu-id="907b6-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="907b6-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="907b6-210">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-210">String</span></span>|
|<span data-ttu-id="907b6-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="907b6-212">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-212">String</span></span>|
|<span data-ttu-id="907b6-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="907b6-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="907b6-214">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-214">Int32</span></span>|
|<span data-ttu-id="907b6-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="907b6-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="907b6-216">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-216">Int32</span></span>|
|<span data-ttu-id="907b6-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="907b6-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="907b6-218">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-218">Int32</span></span>|
|<span data-ttu-id="907b6-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="907b6-219">REMARKS</span></span>|<span data-ttu-id="907b6-220">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-220">String</span></span>|
|<span data-ttu-id="907b6-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="907b6-222">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="907b6-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="907b6-223">ProcedureColumns</span></span>

|<span data-ttu-id="907b6-224">열 이름</span><span class="sxs-lookup"><span data-stu-id="907b6-224">ColumnName</span></span>|<span data-ttu-id="907b6-225">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="907b6-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="907b6-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="907b6-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="907b6-227">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-227">String</span></span>|
|<span data-ttu-id="907b6-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="907b6-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="907b6-229">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-229">String</span></span>|
|<span data-ttu-id="907b6-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="907b6-231">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-231">String</span></span>|
|<span data-ttu-id="907b6-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-232">COLUMN_NAME</span></span>|<span data-ttu-id="907b6-233">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-233">String</span></span>|
|<span data-ttu-id="907b6-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-234">COLUMN_TYPE</span></span>|<span data-ttu-id="907b6-235">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-235">Int16</span></span>|
|<span data-ttu-id="907b6-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-236">DATA_TYPE</span></span>|<span data-ttu-id="907b6-237">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-237">Int16</span></span>|
|<span data-ttu-id="907b6-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-238">TYPE_NAME</span></span>|<span data-ttu-id="907b6-239">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-239">String</span></span>|
|<span data-ttu-id="907b6-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="907b6-240">COLUMN_SIZE</span></span>|<span data-ttu-id="907b6-241">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-241">Int32</span></span>|
|<span data-ttu-id="907b6-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="907b6-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="907b6-243">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-243">Int32</span></span>|
|<span data-ttu-id="907b6-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="907b6-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="907b6-245">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-245">Int16</span></span>|
|<span data-ttu-id="907b6-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="907b6-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="907b6-247">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-247">Int16</span></span>|
|<span data-ttu-id="907b6-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="907b6-248">NULLABLE</span></span>|<span data-ttu-id="907b6-249">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-249">Int16</span></span>|
|<span data-ttu-id="907b6-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="907b6-250">REMARKS</span></span>|<span data-ttu-id="907b6-251">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-251">String</span></span>|
|<span data-ttu-id="907b6-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="907b6-252">COLUMN_DEF</span></span>|<span data-ttu-id="907b6-253">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-253">String</span></span>|
|<span data-ttu-id="907b6-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="907b6-255">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-255">Int16</span></span>|
|<span data-ttu-id="907b6-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="907b6-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="907b6-257">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-257">Int16</span></span>|
|<span data-ttu-id="907b6-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="907b6-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="907b6-259">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-259">Int32</span></span>|
|<span data-ttu-id="907b6-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="907b6-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="907b6-261">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-261">Int32</span></span>|
|<span data-ttu-id="907b6-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="907b6-262">IS_NULLABLE</span></span>|<span data-ttu-id="907b6-263">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-263">String</span></span>|
|<span data-ttu-id="907b6-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="907b6-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="907b6-265">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-265">String</span></span>|
|<span data-ttu-id="907b6-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="907b6-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="907b6-267">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-267">String</span></span>|
|<span data-ttu-id="907b6-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="907b6-269">Byte</span><span class="sxs-lookup"><span data-stu-id="907b6-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="907b6-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="907b6-270">ProcedureParameters</span></span>

|<span data-ttu-id="907b6-271">열 이름</span><span class="sxs-lookup"><span data-stu-id="907b6-271">ColumnName</span></span>|<span data-ttu-id="907b6-272">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="907b6-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="907b6-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="907b6-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="907b6-274">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-274">String</span></span>|
|<span data-ttu-id="907b6-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="907b6-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="907b6-276">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-276">String</span></span>|
|<span data-ttu-id="907b6-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="907b6-278">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-278">String</span></span>|
|<span data-ttu-id="907b6-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-279">COLUMN_NAME</span></span>|<span data-ttu-id="907b6-280">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-280">String</span></span>|
|<span data-ttu-id="907b6-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-281">COLUMN_TYPE</span></span>|<span data-ttu-id="907b6-282">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-282">Int16</span></span>|
|<span data-ttu-id="907b6-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-283">DATA_TYPE</span></span>|<span data-ttu-id="907b6-284">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-284">Int16</span></span>|
|<span data-ttu-id="907b6-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-285">TYPE_NAME</span></span>|<span data-ttu-id="907b6-286">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-286">String</span></span>|
|<span data-ttu-id="907b6-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="907b6-287">COLUMN_SIZE</span></span>|<span data-ttu-id="907b6-288">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-288">Int32</span></span>|
|<span data-ttu-id="907b6-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="907b6-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="907b6-290">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-290">Int32</span></span>|
|<span data-ttu-id="907b6-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="907b6-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="907b6-292">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-292">Int16</span></span>|
|<span data-ttu-id="907b6-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="907b6-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="907b6-294">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-294">Int16</span></span>|
|<span data-ttu-id="907b6-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="907b6-295">NULLABLE</span></span>|<span data-ttu-id="907b6-296">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-296">Int16</span></span>|
|<span data-ttu-id="907b6-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="907b6-297">REMARKS</span></span>|<span data-ttu-id="907b6-298">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-298">String</span></span>|
|<span data-ttu-id="907b6-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="907b6-299">COLUMN_DEF</span></span>|<span data-ttu-id="907b6-300">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-300">String</span></span>|
|<span data-ttu-id="907b6-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="907b6-302">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-302">Int16</span></span>|
|<span data-ttu-id="907b6-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="907b6-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="907b6-304">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-304">Int16</span></span>|
|<span data-ttu-id="907b6-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="907b6-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="907b6-306">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-306">Int32</span></span>|
|<span data-ttu-id="907b6-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="907b6-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="907b6-308">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-308">Int32</span></span>|
|<span data-ttu-id="907b6-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="907b6-309">IS_NULLABLE</span></span>|<span data-ttu-id="907b6-310">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-310">String</span></span>|
|<span data-ttu-id="907b6-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="907b6-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="907b6-312">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-312">String</span></span>|
|<span data-ttu-id="907b6-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="907b6-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="907b6-314">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-314">String</span></span>|
|<span data-ttu-id="907b6-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="907b6-316">Byte</span><span class="sxs-lookup"><span data-stu-id="907b6-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="907b6-317">Microsoft Oracle ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="907b6-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="907b6-318">Microsoft SQL Server Oracle ODBC Driver에서는 공통 스키마 컬렉션 외에도 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="907b6-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="907b6-319">Tables</span><span class="sxs-lookup"><span data-stu-id="907b6-319">Tables</span></span>

- <span data-ttu-id="907b6-320">Columns</span><span class="sxs-lookup"><span data-stu-id="907b6-320">Columns</span></span>

- <span data-ttu-id="907b6-321">절차</span><span class="sxs-lookup"><span data-stu-id="907b6-321">Procedures</span></span>

- <span data-ttu-id="907b6-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="907b6-322">ProcedureColumns</span></span>

- <span data-ttu-id="907b6-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="907b6-323">ProcedureParameters</span></span>

- <span data-ttu-id="907b6-324">뷰</span><span class="sxs-lookup"><span data-stu-id="907b6-324">Views</span></span>

- <span data-ttu-id="907b6-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="907b6-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="907b6-326">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="907b6-326">Tables and Views</span></span>

|<span data-ttu-id="907b6-327">열 이름</span><span class="sxs-lookup"><span data-stu-id="907b6-327">ColumnName</span></span>|<span data-ttu-id="907b6-328">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="907b6-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="907b6-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="907b6-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="907b6-330">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-330">String</span></span>|
|<span data-ttu-id="907b6-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="907b6-331">TABLE_OWNER</span></span>|<span data-ttu-id="907b6-332">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-332">String</span></span>|
|<span data-ttu-id="907b6-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-333">TABLE_NAME</span></span>|<span data-ttu-id="907b6-334">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-334">String</span></span>|
|<span data-ttu-id="907b6-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-335">TABLE_TYPE</span></span>|<span data-ttu-id="907b6-336">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-336">String</span></span>|
|<span data-ttu-id="907b6-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="907b6-337">REMARKS</span></span>|<span data-ttu-id="907b6-338">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="907b6-339">Columns</span><span class="sxs-lookup"><span data-stu-id="907b6-339">Columns</span></span>

|<span data-ttu-id="907b6-340">열 이름</span><span class="sxs-lookup"><span data-stu-id="907b6-340">ColumnName</span></span>|<span data-ttu-id="907b6-341">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="907b6-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="907b6-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="907b6-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="907b6-343">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-343">String</span></span>|
|<span data-ttu-id="907b6-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="907b6-344">TABLE_OWNER</span></span>|<span data-ttu-id="907b6-345">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-345">String</span></span>|
|<span data-ttu-id="907b6-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-346">TABLE_NAME</span></span>|<span data-ttu-id="907b6-347">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-347">String</span></span>|
|<span data-ttu-id="907b6-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-348">COLUMN_NAME</span></span>|<span data-ttu-id="907b6-349">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-349">String</span></span>|
|<span data-ttu-id="907b6-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-350">DATA_TYPE</span></span>|<span data-ttu-id="907b6-351">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-351">Int16</span></span>|
|<span data-ttu-id="907b6-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-352">TYPE_NAME</span></span>|<span data-ttu-id="907b6-353">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-353">String</span></span>|
|<span data-ttu-id="907b6-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="907b6-354">PRECISION</span></span>|<span data-ttu-id="907b6-355">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-355">Int32</span></span>|
|<span data-ttu-id="907b6-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="907b6-356">LENGTH</span></span>|<span data-ttu-id="907b6-357">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-357">Int32</span></span>|
|<span data-ttu-id="907b6-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="907b6-358">SCALE</span></span>|<span data-ttu-id="907b6-359">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-359">Int16</span></span>|
|<span data-ttu-id="907b6-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="907b6-360">RADIX</span></span>|<span data-ttu-id="907b6-361">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-361">Int16</span></span>|
|<span data-ttu-id="907b6-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="907b6-362">NULLABLE</span></span>|<span data-ttu-id="907b6-363">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-363">Int16</span></span>|
|<span data-ttu-id="907b6-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="907b6-364">REMARKS</span></span>|<span data-ttu-id="907b6-365">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-365">String</span></span>|
|<span data-ttu-id="907b6-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="907b6-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="907b6-367">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="907b6-368">절차</span><span class="sxs-lookup"><span data-stu-id="907b6-368">Procedures</span></span>

|<span data-ttu-id="907b6-369">열 이름</span><span class="sxs-lookup"><span data-stu-id="907b6-369">ColumnName</span></span>|<span data-ttu-id="907b6-370">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="907b6-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="907b6-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="907b6-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="907b6-372">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-372">String</span></span>|
|<span data-ttu-id="907b6-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="907b6-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="907b6-374">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-374">String</span></span>|
|<span data-ttu-id="907b6-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="907b6-376">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-376">String</span></span>|
|<span data-ttu-id="907b6-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="907b6-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="907b6-378">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-378">Int16</span></span>|
|<span data-ttu-id="907b6-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="907b6-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="907b6-380">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-380">Int16</span></span>|
|<span data-ttu-id="907b6-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="907b6-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="907b6-382">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-382">Int16</span></span>|
|<span data-ttu-id="907b6-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="907b6-383">REMARKS</span></span>|<span data-ttu-id="907b6-384">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-384">String</span></span>|
|<span data-ttu-id="907b6-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="907b6-386">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="907b6-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="907b6-387">ProcedureColumns</span></span>

|<span data-ttu-id="907b6-388">열 이름</span><span class="sxs-lookup"><span data-stu-id="907b6-388">ColumnName</span></span>|<span data-ttu-id="907b6-389">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="907b6-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="907b6-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="907b6-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="907b6-391">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-391">String</span></span>|
|<span data-ttu-id="907b6-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="907b6-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="907b6-393">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-393">String</span></span>|
|<span data-ttu-id="907b6-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="907b6-395">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-395">String</span></span>|
|<span data-ttu-id="907b6-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-396">COLUMN_NAME</span></span>|<span data-ttu-id="907b6-397">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-397">String</span></span>|
|<span data-ttu-id="907b6-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-398">COLUMN_TYPE</span></span>|<span data-ttu-id="907b6-399">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-399">Int16</span></span>|
|<span data-ttu-id="907b6-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-400">DATA_TYPE</span></span>|<span data-ttu-id="907b6-401">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-401">Int16</span></span>|
|<span data-ttu-id="907b6-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-402">TYPE_NAME</span></span>|<span data-ttu-id="907b6-403">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-403">String</span></span>|
|<span data-ttu-id="907b6-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="907b6-404">PRECISION</span></span>|<span data-ttu-id="907b6-405">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-405">Int32</span></span>|
|<span data-ttu-id="907b6-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="907b6-406">LENGTH</span></span>|<span data-ttu-id="907b6-407">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-407">Int32</span></span>|
|<span data-ttu-id="907b6-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="907b6-408">SCALE</span></span>|<span data-ttu-id="907b6-409">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-409">Int16</span></span>|
|<span data-ttu-id="907b6-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="907b6-410">RADIX</span></span>|<span data-ttu-id="907b6-411">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-411">Int16</span></span>|
|<span data-ttu-id="907b6-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="907b6-412">NULLABLE</span></span>|<span data-ttu-id="907b6-413">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-413">Int16</span></span>|
|<span data-ttu-id="907b6-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="907b6-414">REMARKS</span></span>|<span data-ttu-id="907b6-415">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-415">String</span></span>|
|<span data-ttu-id="907b6-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="907b6-416">OVERLOAD</span></span>|<span data-ttu-id="907b6-417">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-417">Int32</span></span>|
|<span data-ttu-id="907b6-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="907b6-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="907b6-419">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="907b6-420">Microsoft Jet ODBC Driver</span><span class="sxs-lookup"><span data-stu-id="907b6-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="907b6-421">Microsoft Jet ODBC Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="907b6-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="907b6-422">Tables</span><span class="sxs-lookup"><span data-stu-id="907b6-422">Tables</span></span>

- <span data-ttu-id="907b6-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="907b6-423">Indexes</span></span>

- <span data-ttu-id="907b6-424">Columns</span><span class="sxs-lookup"><span data-stu-id="907b6-424">Columns</span></span>

- <span data-ttu-id="907b6-425">절차</span><span class="sxs-lookup"><span data-stu-id="907b6-425">Procedures</span></span>

- <span data-ttu-id="907b6-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="907b6-426">ProcedureColumns</span></span>

- <span data-ttu-id="907b6-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="907b6-427">ProcedureParameters</span></span>

- <span data-ttu-id="907b6-428">뷰</span><span class="sxs-lookup"><span data-stu-id="907b6-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="907b6-429">Tables 및 Views</span><span class="sxs-lookup"><span data-stu-id="907b6-429">Tables and Views</span></span>

|<span data-ttu-id="907b6-430">열 이름</span><span class="sxs-lookup"><span data-stu-id="907b6-430">ColumnName</span></span>|<span data-ttu-id="907b6-431">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="907b6-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="907b6-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="907b6-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="907b6-433">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-433">String</span></span>|
|<span data-ttu-id="907b6-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="907b6-434">TABLE_OWNER</span></span>|<span data-ttu-id="907b6-435">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-435">String</span></span>|
|<span data-ttu-id="907b6-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-436">TABLE_NAME</span></span>|<span data-ttu-id="907b6-437">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-437">String</span></span>|
|<span data-ttu-id="907b6-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-438">TABLE_TYPE</span></span>|<span data-ttu-id="907b6-439">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-439">String</span></span>|
|<span data-ttu-id="907b6-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="907b6-440">REMARKS</span></span>|<span data-ttu-id="907b6-441">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="907b6-442">Columns</span><span class="sxs-lookup"><span data-stu-id="907b6-442">Columns</span></span>

|<span data-ttu-id="907b6-443">열 이름</span><span class="sxs-lookup"><span data-stu-id="907b6-443">ColumnName</span></span>|<span data-ttu-id="907b6-444">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="907b6-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="907b6-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="907b6-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="907b6-446">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-446">String</span></span>|
|<span data-ttu-id="907b6-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="907b6-447">TABLE_OWNER</span></span>|<span data-ttu-id="907b6-448">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-448">String</span></span>|
|<span data-ttu-id="907b6-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-449">TABLE_NAME</span></span>|<span data-ttu-id="907b6-450">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-450">String</span></span>|
|<span data-ttu-id="907b6-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-451">COLUMN_NAME</span></span>|<span data-ttu-id="907b6-452">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-452">String</span></span>|
|<span data-ttu-id="907b6-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-453">DATA_TYPE</span></span>|<span data-ttu-id="907b6-454">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-454">Int16</span></span>|
|<span data-ttu-id="907b6-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-455">TYPE_NAME</span></span>|<span data-ttu-id="907b6-456">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-456">String</span></span>|
|<span data-ttu-id="907b6-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="907b6-457">PRECISION</span></span>|<span data-ttu-id="907b6-458">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-458">Int32</span></span>|
|<span data-ttu-id="907b6-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="907b6-459">LENGTH</span></span>|<span data-ttu-id="907b6-460">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-460">Int32</span></span>|
|<span data-ttu-id="907b6-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="907b6-461">SCALE</span></span>|<span data-ttu-id="907b6-462">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-462">Int16</span></span>|
|<span data-ttu-id="907b6-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="907b6-463">RADIX</span></span>|<span data-ttu-id="907b6-464">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-464">Int16</span></span>|
|<span data-ttu-id="907b6-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="907b6-465">NULLABLE</span></span>|<span data-ttu-id="907b6-466">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-466">Int16</span></span>|
|<span data-ttu-id="907b6-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="907b6-467">REMARKS</span></span>|<span data-ttu-id="907b6-468">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-468">String</span></span>|
|<span data-ttu-id="907b6-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="907b6-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="907b6-470">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="907b6-471">절차</span><span class="sxs-lookup"><span data-stu-id="907b6-471">Procedures</span></span>

|<span data-ttu-id="907b6-472">열 이름</span><span class="sxs-lookup"><span data-stu-id="907b6-472">ColumnName</span></span>|<span data-ttu-id="907b6-473">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="907b6-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="907b6-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="907b6-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="907b6-475">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-475">String</span></span>|
|<span data-ttu-id="907b6-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="907b6-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="907b6-477">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-477">String</span></span>|
|<span data-ttu-id="907b6-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="907b6-479">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-479">String</span></span>|
|<span data-ttu-id="907b6-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="907b6-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="907b6-481">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-481">Int16</span></span>|
|<span data-ttu-id="907b6-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="907b6-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="907b6-483">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-483">Int16</span></span>|
|<span data-ttu-id="907b6-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="907b6-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="907b6-485">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-485">Int16</span></span>|
|<span data-ttu-id="907b6-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="907b6-486">REMARKS</span></span>|<span data-ttu-id="907b6-487">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-487">String</span></span>|
|<span data-ttu-id="907b6-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="907b6-489">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="907b6-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="907b6-490">ProcedureColumns</span></span>

|<span data-ttu-id="907b6-491">열 이름</span><span class="sxs-lookup"><span data-stu-id="907b6-491">ColumnName</span></span>|<span data-ttu-id="907b6-492">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="907b6-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="907b6-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="907b6-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="907b6-494">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-494">String</span></span>|
|<span data-ttu-id="907b6-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="907b6-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="907b6-496">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-496">String</span></span>|
|<span data-ttu-id="907b6-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="907b6-498">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-498">String</span></span>|
|<span data-ttu-id="907b6-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-499">COLUMN_NAME</span></span>|<span data-ttu-id="907b6-500">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-500">String</span></span>|
|<span data-ttu-id="907b6-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-501">COLUMN_TYPE</span></span>|<span data-ttu-id="907b6-502">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-502">Int16</span></span>|
|<span data-ttu-id="907b6-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-503">DATA_TYPE</span></span>|<span data-ttu-id="907b6-504">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-504">Int16</span></span>|
|<span data-ttu-id="907b6-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-505">TYPE_NAME</span></span>|<span data-ttu-id="907b6-506">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-506">String</span></span>|
|<span data-ttu-id="907b6-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="907b6-507">PRECISION</span></span>|<span data-ttu-id="907b6-508">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-508">Int32</span></span>|
|<span data-ttu-id="907b6-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="907b6-509">LENGTH</span></span>|<span data-ttu-id="907b6-510">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-510">Int32</span></span>|
|<span data-ttu-id="907b6-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="907b6-511">SCALE</span></span>|<span data-ttu-id="907b6-512">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-512">Int16</span></span>|
|<span data-ttu-id="907b6-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="907b6-513">RADIX</span></span>|<span data-ttu-id="907b6-514">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-514">Int16</span></span>|
|<span data-ttu-id="907b6-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="907b6-515">NULLABLE</span></span>|<span data-ttu-id="907b6-516">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-516">Int16</span></span>|
|<span data-ttu-id="907b6-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="907b6-517">REMARKS</span></span>|<span data-ttu-id="907b6-518">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-518">String</span></span>|
|<span data-ttu-id="907b6-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="907b6-519">OVERLOAD</span></span>|<span data-ttu-id="907b6-520">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-520">Int32</span></span>|
|<span data-ttu-id="907b6-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="907b6-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="907b6-522">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="907b6-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="907b6-523">ProcedureParameters</span></span>

|<span data-ttu-id="907b6-524">열 이름</span><span class="sxs-lookup"><span data-stu-id="907b6-524">ColumnName</span></span>|<span data-ttu-id="907b6-525">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="907b6-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="907b6-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="907b6-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="907b6-527">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-527">String</span></span>|
|<span data-ttu-id="907b6-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="907b6-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="907b6-529">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-529">String</span></span>|
|<span data-ttu-id="907b6-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="907b6-531">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-531">String</span></span>|
|<span data-ttu-id="907b6-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-532">COLUMN_NAME</span></span>|<span data-ttu-id="907b6-533">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-533">String</span></span>|
|<span data-ttu-id="907b6-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-534">COLUMN_TYPE</span></span>|<span data-ttu-id="907b6-535">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-535">Int16</span></span>|
|<span data-ttu-id="907b6-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-536">DATA_TYPE</span></span>|<span data-ttu-id="907b6-537">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-537">Int16</span></span>|
|<span data-ttu-id="907b6-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="907b6-538">TYPE_NAME</span></span>|<span data-ttu-id="907b6-539">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-539">String</span></span>|
|<span data-ttu-id="907b6-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="907b6-540">COLUMN_SIZE</span></span>|<span data-ttu-id="907b6-541">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-541">Int32</span></span>|
|<span data-ttu-id="907b6-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="907b6-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="907b6-543">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-543">Int32</span></span>|
|<span data-ttu-id="907b6-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="907b6-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="907b6-545">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-545">Int16</span></span>|
|<span data-ttu-id="907b6-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="907b6-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="907b6-547">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-547">Int16</span></span>|
|<span data-ttu-id="907b6-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="907b6-548">NULLABLE</span></span>|<span data-ttu-id="907b6-549">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-549">Int16</span></span>|
|<span data-ttu-id="907b6-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="907b6-550">REMARKS</span></span>|<span data-ttu-id="907b6-551">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-551">String</span></span>|
|<span data-ttu-id="907b6-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="907b6-552">COLUMN_DEF</span></span>|<span data-ttu-id="907b6-553">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-553">String</span></span>|
|<span data-ttu-id="907b6-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="907b6-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="907b6-555">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-555">Int16</span></span>|
|<span data-ttu-id="907b6-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="907b6-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="907b6-557">Int16</span><span class="sxs-lookup"><span data-stu-id="907b6-557">Int16</span></span>|
|<span data-ttu-id="907b6-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="907b6-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="907b6-559">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-559">Int32</span></span>|
|<span data-ttu-id="907b6-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="907b6-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="907b6-561">Int32</span><span class="sxs-lookup"><span data-stu-id="907b6-561">Int32</span></span>|
|<span data-ttu-id="907b6-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="907b6-562">IS_NULLABLE</span></span>|<span data-ttu-id="907b6-563">문자열</span><span class="sxs-lookup"><span data-stu-id="907b6-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="907b6-564">참고자료</span><span class="sxs-lookup"><span data-stu-id="907b6-564">See also</span></span>

- [<span data-ttu-id="907b6-565">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="907b6-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
