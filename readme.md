# Leaderboard Data Migration and Storage Strategy

This document outlines the strategy used to migrate our leaderboard data from a fragmented, per-score model to a consolidated, per-user profile model. This approach significantly improves query efficiency, reduces database clutter, and simplifies data management.

## 1. The Problem: One Row Per Score

Our initial leaderboard system stored every single game played as a separate row in the database.

**Old Data Structure (`leaderboard_scores_v3` collection):**
```json
{
  "id": "abc-123",
  "username": "player1",
  "score": 150,
  "level": 8,
  "difficulty": "easy",
  "replayDataUrl": "https://...",
  "timestamp": "2023-10-27T10:00:00Z"
}