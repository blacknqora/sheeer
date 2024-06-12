# sheeer
sherrrr
class ToneEnum(str, Enum):
    positive = "positive"
    negative = "negative"


class Email(BaseModel):
    """Relevant information about an email."""

    sender: Optional[str] = Field(None, description="The sender's name, if available")
    sender_phone_number: Optional[str] = Field(None, description="The sender's phone number, if available")
    sender_address: Optional[str] = Field(None, description="The sender's address, if available")
    action_items: List[str] = Field(..., description="A list of action items requested by the email")
    topic: str = Field(..., description="High level description of what the email is about")
    tone: ToneEnum = Field(..., description="The tone of the email.")
