# Agent Glossary

## Context

Information currently available to the LLM for making its next prediction or decision.

## Tool Call

A request produced by the LLM asking the controller to execute a specific tool with specific arguments.

## Controller

Program logic that manages the Agent loop, interprets model outputs, executes allowed tools and determines when execution stops.

## Tool

A callable capability that performs a concrete action or retrieves external information.

## Tool Result

The output produced after a tool is executed and returned to the Agent context.

## Agent Loop

A repeated process such as:

Context
→ LLM
→ Action / Tool Call
→ Tool Result
→ Updated Context
→ LLM
