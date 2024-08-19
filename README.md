# Modification

Added extra logic for select (left join and right outer join).

    {
        "where": {
            "foo": "bar"
        },
        "leftJoin": {
            "relationName": {
                "relatedModelPropName": "value"
            }
        }
    }

SQL generated will look somthing like this:

    SELECT 
        Model."id",
        Model."foo"
    FROM
        "public"."model" AS Model
    LEFT JOIN
        "public"."relatedModel" AS RelatedModel ON RelatedModel."dependsOfRelationTypeAndForeignKey" = Model."dependsOfRelationTypeAndForeignKey"
    WHERE
        Model."foo" = "bar" AND RelatedModel."relatedModelPropName" = "value"
    GROUP BY
        Model."id"

# LoopBack Connector

[![CI](https://github.com/loopbackio/loopback-connector/actions/workflows/continuous-integration.yaml/badge.svg)](https://github.com/loopbackio/loopback-connector/actions/workflows/continuous-integration.yaml)

LoopBack Connector is a set of building blocks simplifying implementation
of datasource-specific connectors like Oracle, MongoDB, REST.

**For full documentation, see the official LoopBack documentation**:
 * [Data sources and connectors](https://loopback.io/doc/en/lb4/Connectors-reference.html)

## Installation

    npm install loopback-connector

## Usage

See [loopback-connector-mysql](https://github.com/loopbackio/loopback-connector-mysql) 
for an example of connector using this module.
